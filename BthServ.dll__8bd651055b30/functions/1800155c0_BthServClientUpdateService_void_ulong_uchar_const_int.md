# BthServClientUpdateService(void *,ulong,uchar * const,int)

- ea: `0x1800155c0`
- end: `0x1800156b3`
- name: `?BthServClientUpdateService@@YAKPEAXKQEAEH@Z`
- size: `243`
- prototype: `unsigned int(void *, unsigned int, unsigned __int8 *const, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180012cc0`
- `0x180025e24`

## callees

- `0x18000d404`
- `0x18000f2e8`
- `0x1800155c0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001569b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001569b`

## pseudocode

```c
__int64 __fastcall BthServClientUpdateService(void *a1, DWORD a2, unsigned __int8 *const a3, int a4)
{
  DWORD v8; // edi
  volatile signed __int32 *v9; // rbx
  HANDLE *v10; // [rsp+40h] [rbp-18h] BYREF
  volatile signed __int32 *v11; // [rsp+48h] [rbp-10h]
  DWORD NumberOfBytesTransferred; // [rsp+68h] [rbp+10h] BYREF

  NumberOfBytesTransferred = 0;
  if ( a2 < 0x72A )
    return 122;
  BthServGlobals::GetSafeRadioHandle(&Globals, &v10);
  if ( v10 && (char *)*v10 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v8 = BthServOverlappedIoctl(*v10, 0x411030u, a3, a2, 0, 0, &NumberOfBytesTransferred);
  else
    v8 = 6;
  v9 = v11;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  if ( !v8 )
  {
    if ( a4 )
      Sleep(0xBB8u);
  }
  return v8;
}

```

## disassembly

```asm
0x1800155c0  mov     [rsp+arg_0], rbx
0x1800155c5  mov     [rsp+arg_10], rsi
0x1800155ca  push    rdi
0x1800155cb  sub     rsp, 50h
0x1800155cf  mov     [rsp+58h+NumberOfBytesTransferred], 0
0x1800155d7  mov     esi, r9d
0x1800155da  mov     rdi, r8
0x1800155dd  mov     ebx, edx
0x1800155df  cmp     edx, 72Ah
0x1800155e5  jnb     short loc_1800155F1
0x1800155e7  mov     eax, 7Ah ; 'z'
0x1800155ec  jmp     loc_1800156A3
0x1800155f1  lea     rdx, [rsp+58h+var_18]
0x1800155f6  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x1800155fd  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x180015602  mov     rax, [rsp+58h+var_18]
0x180015607  test    rax, rax
0x18001560a  jz      short loc_180015648
0x18001560c  mov     rcx, [rax]; hFile
0x18001560f  lea     rax, [rcx-1]
0x180015613  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015617  ja      short loc_180015648
0x180015619  lea     rax, [rsp+58h+NumberOfBytesTransferred]
0x18001561e  mov     r9d, ebx; nInBufferSize
0x180015621  mov     [rsp+58h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180015626  mov     r8, rdi; lpInBuffer
0x180015629  mov     [rsp+58h+var_30], 0; DWORD
0x180015631  mov     edx, 411030h; dwIoControlCode
0x180015636  mov     [rsp+58h+var_38], 0; void *
0x18001563f  call    ?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z; BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x180015644  mov     edi, eax
0x180015646  jmp     short loc_18001564D
0x180015648  mov     edi, 6
0x18001564d  mov     rbx, [rsp+58h+var_10]
0x180015652  test    rbx, rbx
0x180015655  jz      short loc_18001568E
0x180015657  or      eax, 0FFFFFFFFh
0x18001565a  lock xadd [rbx+8], eax
0x18001565f  cmp     eax, 1
0x180015662  jnz     short loc_18001568E
0x180015664  mov     rax, [rbx]
0x180015667  mov     rcx, rbx
0x18001566a  mov     rax, [rax]
0x18001566d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015672  or      eax, 0FFFFFFFFh
0x180015675  lock xadd [rbx+0Ch], eax
0x18001567a  cmp     eax, 1
0x18001567d  jnz     short loc_18001568E
0x18001567f  mov     rax, [rbx]
0x180015682  mov     rcx, rbx
0x180015685  mov     rax, [rax+8]
0x180015689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001568e  test    edi, edi
0x180015690  jnz     short loc_1800156A1
0x180015692  test    esi, esi
0x180015694  jz      short loc_1800156A1
0x180015696  mov     ecx, 0BB8h; dwMilliseconds
0x18001569b  call    cs:__imp_Sleep
0x1800156a1  mov     eax, edi
0x1800156a3  mov     rbx, [rsp+58h+arg_0]
0x1800156a8  mov     rsi, [rsp+58h+arg_10]
0x1800156ad  add     rsp, 50h
0x1800156b1  pop     rdi
0x1800156b2  retn
```
