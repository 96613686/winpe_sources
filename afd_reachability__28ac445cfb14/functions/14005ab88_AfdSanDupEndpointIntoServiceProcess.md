# AfdSanDupEndpointIntoServiceProcess

- ea: `0x14005ab88`
- end: `0x14005ad8a`
- name: `AfdSanDupEndpointIntoServiceProcess`
- size: `514`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005c880`

## callees

- `0x14000f390`
- `0x140019190`
- `0x1400191f0`
- `0x14005ab88`
- `0x14005db88`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14005abb7`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14005abb7`
- `ntoskrnl!IoSetIoCompletion` at `0x14005ac88`
- `ntoskrnl!IoSetIoCompletion` at `0x14005ac88`
- `ntoskrnl!ObCloseHandle` at `0x14005ad42`
- `ntoskrnl!ObCloseHandle` at `0x14005ad42`
- `ntoskrnl!KeAttachProcess` at `0x14005abd7`
- `ntoskrnl!KeAttachProcess` at `0x14005ad2f`
- `ntoskrnl!KeAttachProcess` at `0x14005abd7`
- `ntoskrnl!KeAttachProcess` at `0x14005ad2f`
- `ntoskrnl!KeDetachProcess` at `0x14005ac1f`
- `ntoskrnl!KeDetachProcess` at `0x14005ad4e`
- `ntoskrnl!KeDetachProcess` at `0x14005ac1f`
- `ntoskrnl!KeDetachProcess` at `0x14005ad4e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14005ac11`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14005ac11`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005ad68`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005ad68`
- `ntoskrnl!IoFileObjectType` at `0x14005abf6`

## pseudocode

```c
__int64 __fastcall AfdSanDupEndpointIntoServiceProcess(_QWORD *Object, __int64 a2, int a3)
{
  __int64 v3; // rdi
  NTSTATUS v7; // ebx
  __int64 v8; // rsi
  HANDLE Handle; // [rsp+60h] [rbp+8h] BYREF

  v3 = Object[3];
  Handle = 0;
  ExEnterCriticalRegionAndAcquireResourceShared(AfdGlobalData);
  if ( !AfdSanServiceHelper )
  {
    v7 = -1073741823;
    goto LABEL_17;
  }
  KeAttachProcess(*(PRKPROCESS *)(AfdSanServiceHelper + 48));
  v7 = ObOpenObjectByPointer(Object, 0x40u, 0, 0x2000000u, (POBJECT_TYPE)IoFileObjectType, 1, &Handle);
  KeDetachProcess();
  if ( v7 >= 0 )
  {
    v8 = AfdLockEndpointContext(v3);
    if ( *(_QWORD *)(v3 + 96) == AfdSanServiceHelper )
    {
      v7 = -1073741811;
    }
    else
    {
      if ( (_InterlockedExchangeAdd((volatile signed __int32 *)(AfdSanServiceHelper + 132), 2u) & 1) != 0 )
      {
        v7 = -1073741536;
      }
      else
      {
        v7 = IoSetIoCompletion(*(_QWORD *)(AfdSanServiceHelper + 112), 0, 5);
        if ( v7 >= 0 )
        {
          if ( (unsigned __int8)AfdSanSetDupingToServiceState(v3) )
          {
            AfdDereferenceEndpoint(*(_QWORD *)(v3 + 96));
            if ( _InterlockedIncrement64((volatile signed __int64 *)(AfdSanServiceHelper + 64)) <= 1 )
              __fastfail(0xEu);
            *(_QWORD *)(v3 + 96) = AfdSanServiceHelper;
            *(_QWORD *)(v3 + 112) = a2;
            *(_DWORD *)(v3 + 144) = a3;
            *(_BYTE *)(v3 + 160) = 1;
          }
          else
          {
            v7 = -1073741536;
          }
          AfdUnlockEndpointContext(v3, v8);
          goto LABEL_17;
        }
      }
      _InterlockedAdd((volatile signed __int32 *)(AfdSanServiceHelper + 132), 0xFFFFFFFE);
    }
    AfdUnlockEndpointContext(v3, v8);
    KeAttachProcess(*(PRKPROCESS *)(*(_QWORD *)(v3 + 96) + 48LL));
    ObCloseHandle(Handle, 1);
    KeDetachProcess();
  }
LABEL_17:
  ExReleaseResourceAndLeaveCriticalRegion(AfdGlobalData);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14005ab88  mov     [rsp+arg_8], rbx
0x14005ab8d  mov     [rsp+arg_10], rbp
0x14005ab92  push    rsi
0x14005ab93  push    rdi
0x14005ab94  push    r14
0x14005ab96  sub     rsp, 40h
0x14005ab9a  mov     rdi, [rcx+18h]
0x14005ab9e  mov     rbx, rcx
0x14005aba1  mov     rcx, cs:AfdGlobalData; Resource
0x14005aba8  mov     ebp, r8d
0x14005abab  mov     r14, rdx
0x14005abae  mov     [rsp+58h+arg_0], 0
0x14005abb7  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x14005abbe  nop     dword ptr [rax+rax+00h]
0x14005abc3  mov     rcx, cs:AfdSanServiceHelper
0x14005abca  test    rcx, rcx
0x14005abcd  jz      loc_14005AD5C
0x14005abd3  mov     rcx, [rcx+30h]; Process
0x14005abd7  call    cs:__imp_KeAttachProcess
0x14005abde  nop     dword ptr [rax+rax+00h]
0x14005abe3  lea     rax, [rsp+58h+arg_0]
0x14005abe8  xor     r8d, r8d; PassedAccessState
0x14005abeb  mov     [rsp+58h+Handle], rax; Handle
0x14005abf0  mov     r9d, 2000000h; DesiredAccess
0x14005abf6  mov     rax, cs:__imp_IoFileObjectType
0x14005abfd  mov     [rsp+58h+AccessMode], 1; AccessMode
0x14005ac02  lea     edx, [r8+40h]; HandleAttributes
0x14005ac06  mov     rcx, [rax]
0x14005ac09  mov     [rsp+58h+ObjectType], rcx; ObjectType
0x14005ac0e  mov     rcx, rbx; Object
0x14005ac11  call    cs:__imp_ObOpenObjectByPointer
0x14005ac18  nop     dword ptr [rax+rax+00h]
0x14005ac1d  mov     ebx, eax
0x14005ac1f  call    cs:__imp_KeDetachProcess
0x14005ac26  nop     dword ptr [rax+rax+00h]
0x14005ac2b  test    ebx, ebx
0x14005ac2d  js      loc_14005AD61
0x14005ac33  mov     rcx, rdi
0x14005ac36  call    AfdLockEndpointContext
0x14005ac3b  mov     rdx, cs:AfdSanServiceHelper
0x14005ac42  mov     rsi, rax
0x14005ac45  cmp     [rdi+60h], rdx
0x14005ac49  jz      loc_14005AD17
0x14005ac4f  mov     ecx, 2
0x14005ac54  lock xadd [rdx+84h], ecx
0x14005ac5c  test    cl, 1
0x14005ac5f  jnz     loc_14005AD01
0x14005ac65  mov     rcx, [rsp+58h+arg_0]
0x14005ac6a  xor     r9d, r9d
0x14005ac6d  mov     [rsp+58h+AccessMode], 1
0x14005ac72  xor     edx, edx
0x14005ac74  mov     [rsp+58h+ObjectType], rcx
0x14005ac79  mov     rcx, cs:AfdSanServiceHelper
0x14005ac80  lea     r8d, [r9+5]
0x14005ac84  mov     rcx, [rcx+70h]
0x14005ac88  call    cs:__imp_IoSetIoCompletion
0x14005ac8f  nop     dword ptr [rax+rax+00h]
0x14005ac94  mov     ebx, eax
0x14005ac96  test    eax, eax
0x14005ac98  js      short loc_14005AD06
0x14005ac9a  mov     rcx, rdi
0x14005ac9d  call    AfdSanSetDupingToServiceState
0x14005aca2  test    al, al
0x14005aca4  jz      short loc_14005ACEF
0x14005aca6  mov     rcx, [rdi+60h]
0x14005acaa  call    AfdDereferenceEndpoint
0x14005acaf  mov     rax, cs:AfdSanServiceHelper
0x14005acb6  mov     ecx, 1
0x14005acbb  lock xadd [rax+40h], rcx
0x14005acc1  inc     rcx
0x14005acc4  cmp     rcx, 1
0x14005acc8  jg      short loc_14005ACD1
0x14005acca  mov     ecx, 0Eh
0x14005accf  int     29h; Win8: RtlFailFast(ecx)
0x14005acd1  mov     rax, cs:AfdSanServiceHelper
0x14005acd8  mov     [rdi+60h], rax
0x14005acdc  mov     [rdi+70h], r14
0x14005ace0  mov     [rdi+90h], ebp
0x14005ace6  mov     byte ptr [rdi+0A0h], 1
0x14005aced  jmp     short loc_14005ACF4
0x14005acef  mov     ebx, 0C0000120h
0x14005acf4  mov     rdx, rsi
0x14005acf7  mov     rcx, rdi
0x14005acfa  call    AfdUnlockEndpointContext
0x14005acff  jmp     short loc_14005AD61
0x14005ad01  mov     ebx, 0C0000120h
0x14005ad06  mov     rax, cs:AfdSanServiceHelper
0x14005ad0d  lock add dword ptr [rax+84h], 0FFFFFFFEh
0x14005ad15  jmp     short loc_14005AD1C
0x14005ad17  mov     ebx, 0C000000Dh
0x14005ad1c  mov     rdx, rsi
0x14005ad1f  mov     rcx, rdi
0x14005ad22  call    AfdUnlockEndpointContext
0x14005ad27  mov     rcx, [rdi+60h]
0x14005ad2b  mov     rcx, [rcx+30h]; Process
0x14005ad2f  call    cs:__imp_KeAttachProcess
0x14005ad36  nop     dword ptr [rax+rax+00h]
0x14005ad3b  mov     rcx, [rsp+58h+arg_0]; Handle
0x14005ad40  mov     dl, 1; PreviousMode
0x14005ad42  call    cs:__imp_ObCloseHandle
0x14005ad49  nop     dword ptr [rax+rax+00h]
0x14005ad4e  call    cs:__imp_KeDetachProcess
0x14005ad55  nop     dword ptr [rax+rax+00h]
0x14005ad5a  jmp     short loc_14005AD61
0x14005ad5c  mov     ebx, 0C0000001h
0x14005ad61  mov     rcx, cs:AfdGlobalData; Resource
0x14005ad68  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14005ad6f  nop     dword ptr [rax+rax+00h]
0x14005ad74  mov     rbp, [rsp+58h+arg_10]
0x14005ad79  mov     eax, ebx
0x14005ad7b  mov     rbx, [rsp+58h+arg_8]
0x14005ad80  add     rsp, 40h
0x14005ad84  pop     r14
0x14005ad86  pop     rdi
0x14005ad87  pop     rsi
0x14005ad88  retn
```
