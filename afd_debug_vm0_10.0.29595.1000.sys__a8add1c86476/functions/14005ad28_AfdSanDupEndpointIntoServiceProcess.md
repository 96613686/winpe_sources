# AfdSanDupEndpointIntoServiceProcess

- ea: `0x14005ad28`
- end: `0x14005af2a`
- name: `AfdSanDupEndpointIntoServiceProcess`
- size: `514`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14005ca20`

## callees

- `0x14000f390`
- `0x140019190`
- `0x1400191f0`
- `0x14005ad28`
- `0x14005dd28`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14005ad57`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x14005ad57`
- `ntoskrnl!IoSetIoCompletion` at `0x14005ae28`
- `ntoskrnl!IoSetIoCompletion` at `0x14005ae28`
- `ntoskrnl!ObCloseHandle` at `0x14005aee2`
- `ntoskrnl!ObCloseHandle` at `0x14005aee2`
- `ntoskrnl!KeAttachProcess` at `0x14005ad77`
- `ntoskrnl!KeAttachProcess` at `0x14005aecf`
- `ntoskrnl!KeAttachProcess` at `0x14005ad77`
- `ntoskrnl!KeAttachProcess` at `0x14005aecf`
- `ntoskrnl!KeDetachProcess` at `0x14005adbf`
- `ntoskrnl!KeDetachProcess` at `0x14005aeee`
- `ntoskrnl!KeDetachProcess` at `0x14005adbf`
- `ntoskrnl!KeDetachProcess` at `0x14005aeee`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14005adb1`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14005adb1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005af08`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x14005af08`
- `ntoskrnl!IoFileObjectType` at `0x14005ad96`

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
0x14005ad28  mov     [rsp+arg_8], rbx
0x14005ad2d  mov     [rsp+arg_10], rbp
0x14005ad32  push    rsi
0x14005ad33  push    rdi
0x14005ad34  push    r14
0x14005ad36  sub     rsp, 40h
0x14005ad3a  mov     rdi, [rcx+18h]
0x14005ad3e  mov     rbx, rcx
0x14005ad41  mov     rcx, cs:AfdGlobalData; Resource
0x14005ad48  mov     ebp, r8d
0x14005ad4b  mov     r14, rdx
0x14005ad4e  mov     [rsp+58h+arg_0], 0
0x14005ad57  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceShared
0x14005ad5e  nop     dword ptr [rax+rax+00h]
0x14005ad63  mov     rcx, cs:AfdSanServiceHelper
0x14005ad6a  test    rcx, rcx
0x14005ad6d  jz      loc_14005AEFC
0x14005ad73  mov     rcx, [rcx+30h]; Process
0x14005ad77  call    cs:__imp_KeAttachProcess
0x14005ad7e  nop     dword ptr [rax+rax+00h]
0x14005ad83  lea     rax, [rsp+58h+arg_0]
0x14005ad88  xor     r8d, r8d; PassedAccessState
0x14005ad8b  mov     [rsp+58h+Handle], rax; Handle
0x14005ad90  mov     r9d, 2000000h; DesiredAccess
0x14005ad96  mov     rax, cs:__imp_IoFileObjectType
0x14005ad9d  mov     [rsp+58h+AccessMode], 1; AccessMode
0x14005ada2  lea     edx, [r8+40h]; HandleAttributes
0x14005ada6  mov     rcx, [rax]
0x14005ada9  mov     [rsp+58h+ObjectType], rcx; ObjectType
0x14005adae  mov     rcx, rbx; Object
0x14005adb1  call    cs:__imp_ObOpenObjectByPointer
0x14005adb8  nop     dword ptr [rax+rax+00h]
0x14005adbd  mov     ebx, eax
0x14005adbf  call    cs:__imp_KeDetachProcess
0x14005adc6  nop     dword ptr [rax+rax+00h]
0x14005adcb  test    ebx, ebx
0x14005adcd  js      loc_14005AF01
0x14005add3  mov     rcx, rdi
0x14005add6  call    AfdLockEndpointContext
0x14005addb  mov     rdx, cs:AfdSanServiceHelper
0x14005ade2  mov     rsi, rax
0x14005ade5  cmp     [rdi+60h], rdx
0x14005ade9  jz      loc_14005AEB7
0x14005adef  mov     ecx, 2
0x14005adf4  lock xadd [rdx+84h], ecx
0x14005adfc  test    cl, 1
0x14005adff  jnz     loc_14005AEA1
0x14005ae05  mov     rcx, [rsp+58h+arg_0]
0x14005ae0a  xor     r9d, r9d
0x14005ae0d  mov     [rsp+58h+AccessMode], 1
0x14005ae12  xor     edx, edx
0x14005ae14  mov     [rsp+58h+ObjectType], rcx
0x14005ae19  mov     rcx, cs:AfdSanServiceHelper
0x14005ae20  lea     r8d, [r9+5]
0x14005ae24  mov     rcx, [rcx+70h]
0x14005ae28  call    cs:__imp_IoSetIoCompletion
0x14005ae2f  nop     dword ptr [rax+rax+00h]
0x14005ae34  mov     ebx, eax
0x14005ae36  test    eax, eax
0x14005ae38  js      short loc_14005AEA6
0x14005ae3a  mov     rcx, rdi
0x14005ae3d  call    AfdSanSetDupingToServiceState
0x14005ae42  test    al, al
0x14005ae44  jz      short loc_14005AE8F
0x14005ae46  mov     rcx, [rdi+60h]
0x14005ae4a  call    AfdDereferenceEndpoint
0x14005ae4f  mov     rax, cs:AfdSanServiceHelper
0x14005ae56  mov     ecx, 1
0x14005ae5b  lock xadd [rax+40h], rcx
0x14005ae61  inc     rcx
0x14005ae64  cmp     rcx, 1
0x14005ae68  jg      short loc_14005AE71
0x14005ae6a  mov     ecx, 0Eh
0x14005ae6f  int     29h; Win8: RtlFailFast(ecx)
0x14005ae71  mov     rax, cs:AfdSanServiceHelper
0x14005ae78  mov     [rdi+60h], rax
0x14005ae7c  mov     [rdi+70h], r14
0x14005ae80  mov     [rdi+90h], ebp
0x14005ae86  mov     byte ptr [rdi+0A0h], 1
0x14005ae8d  jmp     short loc_14005AE94
0x14005ae8f  mov     ebx, 0C0000120h
0x14005ae94  mov     rdx, rsi
0x14005ae97  mov     rcx, rdi
0x14005ae9a  call    AfdUnlockEndpointContext
0x14005ae9f  jmp     short loc_14005AF01
0x14005aea1  mov     ebx, 0C0000120h
0x14005aea6  mov     rax, cs:AfdSanServiceHelper
0x14005aead  lock add dword ptr [rax+84h], 0FFFFFFFEh
0x14005aeb5  jmp     short loc_14005AEBC
0x14005aeb7  mov     ebx, 0C000000Dh
0x14005aebc  mov     rdx, rsi
0x14005aebf  mov     rcx, rdi
0x14005aec2  call    AfdUnlockEndpointContext
0x14005aec7  mov     rcx, [rdi+60h]
0x14005aecb  mov     rcx, [rcx+30h]; Process
0x14005aecf  call    cs:__imp_KeAttachProcess
0x14005aed6  nop     dword ptr [rax+rax+00h]
0x14005aedb  mov     rcx, [rsp+58h+arg_0]; Handle
0x14005aee0  mov     dl, 1; PreviousMode
0x14005aee2  call    cs:__imp_ObCloseHandle
0x14005aee9  nop     dword ptr [rax+rax+00h]
0x14005aeee  call    cs:__imp_KeDetachProcess
0x14005aef5  nop     dword ptr [rax+rax+00h]
0x14005aefa  jmp     short loc_14005AF01
0x14005aefc  mov     ebx, 0C0000001h
0x14005af01  mov     rcx, cs:AfdGlobalData; Resource
0x14005af08  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x14005af0f  nop     dword ptr [rax+rax+00h]
0x14005af14  mov     rbp, [rsp+58h+arg_10]
0x14005af19  mov     eax, ebx
0x14005af1b  mov     rbx, [rsp+58h+arg_8]
0x14005af20  add     rsp, 40h
0x14005af24  pop     r14
0x14005af26  pop     rdi
0x14005af27  pop     rsi
0x14005af28  retn
```
