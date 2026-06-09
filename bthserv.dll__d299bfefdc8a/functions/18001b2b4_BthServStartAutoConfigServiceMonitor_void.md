# BthServStartAutoConfigServiceMonitor(void)

- ea: `0x18001b2b4`
- end: `0x18001b61f`
- name: `?BthServStartAutoConfigServiceMonitor@@YAXXZ`
- size: `875`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000ad78`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x18000d404`
- `0x18000f2e8`
- `0x1800110fc`
- `0x180011194`
- `0x18001b2b4`
- `0x18001b9d8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b475`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b475`

## pseudocode

```c
void BthServStartAutoConfigServiceMonitor(void)
{
  __int64 v0; // r8
  _BYTE *v1; // rcx
  char v2; // si
  bool v3; // dl
  __int64 v4; // rdx
  volatile signed __int32 *v5; // rdi
  bool v6; // dl
  volatile signed __int32 *v7; // rdi
  int v8; // [rsp+20h] [rbp-1C8h]
  DWORD v9; // [rsp+28h] [rbp-1C0h]
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp-198h] BYREF
  HANDLE *v11; // [rsp+58h] [rbp-190h] BYREF
  volatile signed __int32 *v12; // [rsp+60h] [rbp-188h]
  _BYTE v13[304]; // [rsp+70h] [rbp-178h] BYREF

  NumberOfBytesTransferred = 0;
  memset_0(v13, 0, 0x124u);
  v1 = WPP_GLOBAL_Control;
  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  LOBYTE(v0) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v0, *((_QWORD *)WPP_GLOBAL_Control + 5));
    v1 = WPP_GLOBAL_Control;
  }
  if ( !*(_DWORD *)&dword_180044B94 )
    goto LABEL_54;
  BthServGlobals::GetSafeRadioHandle(&Globals, &v11, v0);
  if ( !v11 || (char *)*v11 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v1 = WPP_GLOBAL_Control;
    LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    LOBYTE(v0) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, v0, *((_QWORD *)WPP_GLOBAL_Control + 5));
      goto LABEL_48;
    }
LABEL_49:
    v7 = v12;
    if ( v12 )
    {
      if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64))v7)(v7, v4, v0);
        if ( !_InterlockedDecrement(v7 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
      goto LABEL_53;
    }
    goto LABEL_54;
  }
  if ( BthServOverlappedIoctl(*v11, 0x410000u, 0, 0, v13, 0x124u, &NumberOfBytesTransferred)
    || NumberOfBytesTransferred != 292 )
  {
    v1 = WPP_GLOBAL_Control;
    LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    LOBYTE(v0) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        v0,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v8,
        v9,
        11,
        (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
LABEL_48:
      v1 = WPP_GLOBAL_Control;
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  v5 = v12;
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  if ( v13[278] >= 2u )
  {
    pInterfaceGuid = LocalAlloc(0x40u, 0x80u);
    if ( pInterfaceGuid )
    {
      MonitorAutoConfigService();
      goto LABEL_53;
    }
    v1 = WPP_GLOBAL_Control;
    v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v0) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v0, *((_QWORD *)WPP_GLOBAL_Control + 5));
      goto LABEL_53;
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v0) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        v0,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v8,
        v9,
        13,
        (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
LABEL_53:
      v1 = WPP_GLOBAL_Control;
    }
  }
LABEL_54:
  if ( v1 == (_BYTE *)&WPP_GLOBAL_Control || v1[25] < 4u )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v0) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v1 + 2), v2, v0, *((_QWORD *)v1 + 5));
  }
}

```

## disassembly

```asm
0x18001b2b4  push    rbx
0x18001b2b6  push    rbp
0x18001b2b7  push    rsi
0x18001b2b8  push    rdi
0x18001b2b9  push    r12
0x18001b2bb  push    r14
0x18001b2bd  sub     rsp, 1B8h
0x18001b2c4  mov     rax, cs:__security_cookie
0x18001b2cb  xor     rax, rsp
0x18001b2ce  mov     [rsp+1E8h+var_48], rax
0x18001b2d6  mov     ebx, 124h
0x18001b2db  mov     [rsp+1E8h+NumberOfBytesTransferred], 0
0x18001b2e3  mov     r8d, ebx; Size
0x18001b2e6  lea     rcx, [rsp+1E8h+var_178]; void *
0x18001b2eb  xor     edx, edx; Val
0x18001b2ed  call    memset_0
0x18001b2f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2f9  lea     rbp, WPP_GLOBAL_Control
0x18001b300  mov     sil, 1
0x18001b303  cmp     rcx, rbp
0x18001b306  jz      short loc_18001B313
0x18001b308  cmp     byte ptr [rcx+19h], 4
0x18001b30c  jb      short loc_18001B313
0x18001b30e  mov     dl, sil
0x18001b311  jmp     short loc_18001B315
0x18001b313  xor     dl, dl
0x18001b315  lea     r14, WPP_RECORDER_INITIALIZED
0x18001b31c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001b323  lea     r12, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001b32a  setnz   r8b
0x18001b32e  test    dl, dl
0x18001b330  jnz     short loc_18001B337
0x18001b332  test    r8b, r8b
0x18001b335  jz      short loc_18001B357
0x18001b337  mov     r9, [rcx+28h]
0x18001b33b  mov     rcx, [rcx+10h]
0x18001b33f  mov     [rsp+1E8h+var_1B0], r12
0x18001b344  mov     word ptr [rsp+1E8h+lpNumberOfBytesTransferred], 0Ah
0x18001b34b  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b350  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b357  cmp     cs:dword_180044B94, 0
0x18001b35e  jz      loc_18001B5C0
0x18001b364  lea     rdx, [rsp+1E8h+var_190]
0x18001b369  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x18001b370  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x18001b375  mov     rax, [rsp+1E8h+var_190]
0x18001b37a  test    rax, rax
0x18001b37d  jz      loc_18001B52C
0x18001b383  mov     rcx, [rax]; hFile
0x18001b386  lea     rax, [rcx-1]
0x18001b38a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001b38e  ja      loc_18001B52C
0x18001b394  lea     rax, [rsp+1E8h+NumberOfBytesTransferred]
0x18001b399  xor     r9d, r9d; nInBufferSize
0x18001b39c  mov     [rsp+1E8h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18001b3a1  xor     r8d, r8d; lpInBuffer
0x18001b3a4  lea     rax, [rsp+1E8h+var_178]
0x18001b3a9  mov     [rsp+1E8h+var_1C0], ebx; DWORD
0x18001b3ad  mov     edx, 410000h; dwIoControlCode
0x18001b3b2  mov     [rsp+1E8h+var_1C8], rax; void *
0x18001b3b7  call    ?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z; BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18001b3bc  test    eax, eax
0x18001b3be  jnz     loc_18001B4E0
0x18001b3c4  cmp     [rsp+1E8h+NumberOfBytesTransferred], ebx
0x18001b3c8  jnz     loc_18001B4E0
0x18001b3ce  mov     rdi, [rsp+1E8h+var_188]
0x18001b3d3  test    rdi, rdi
0x18001b3d6  jz      short loc_18001B40E
0x18001b3d8  or      ebx, 0FFFFFFFFh
0x18001b3db  mov     eax, ebx
0x18001b3dd  lock xadd [rdi+8], eax
0x18001b3e2  add     eax, ebx
0x18001b3e4  jnz     short loc_18001B40E
0x18001b3e6  mov     rax, [rdi]
0x18001b3e9  mov     rcx, rdi
0x18001b3ec  mov     rax, [rax]
0x18001b3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3f4  mov     eax, ebx
0x18001b3f6  lock xadd [rdi+0Ch], eax
0x18001b3fb  add     eax, ebx
0x18001b3fd  jnz     short loc_18001B40E
0x18001b3ff  mov     rax, [rdi]
0x18001b402  mov     rcx, rdi
0x18001b405  mov     rax, [rax+8]
0x18001b409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b40e  movzx   eax, [rsp+1E8h+var_62]
0x18001b416  cmp     al, 2
0x18001b418  jnb     short loc_18001B46D
0x18001b41a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b421  cmp     rcx, rbp
0x18001b424  jz      short loc_18001B431
0x18001b426  cmp     byte ptr [rcx+19h], 4
0x18001b42a  jb      short loc_18001B431
0x18001b42c  mov     dl, sil
0x18001b42f  jmp     short loc_18001B433
0x18001b431  xor     dl, dl
0x18001b433  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001b43a  setnz   r8b
0x18001b43e  test    dl, dl
0x18001b440  jnz     short loc_18001B44B
0x18001b442  test    r8b, r8b
0x18001b445  jz      loc_18001B5C0
0x18001b44b  mov     r9, [rcx+28h]
0x18001b44f  mov     rcx, [rcx+10h]
0x18001b453  mov     [rsp+1E8h+var_1A0], eax
0x18001b457  mov     [rsp+1E8h+var_1B0], r12
0x18001b45c  mov     word ptr [rsp+1E8h+lpNumberOfBytesTransferred], 0Dh
0x18001b463  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001b468  jmp     loc_18001B5B9
0x18001b46d  mov     edx, 80h; uBytes
0x18001b472  lea     ecx, [rdx-40h]; uFlags
0x18001b475  call    cs:__imp_LocalAlloc
0x18001b47b  mov     cs:pInterfaceGuid, rax
0x18001b482  test    rax, rax
0x18001b485  jnz     short loc_18001B4D6
0x18001b487  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b48e  cmp     rcx, rbp
0x18001b491  jz      short loc_18001B49E
0x18001b493  cmp     byte ptr [rcx+19h], 3
0x18001b497  jb      short loc_18001B49E
0x18001b499  mov     dl, sil
0x18001b49c  jmp     short loc_18001B4A0
0x18001b49e  xor     dl, dl
0x18001b4a0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001b4a7  setnz   r8b
0x18001b4ab  test    dl, dl
0x18001b4ad  jnz     short loc_18001B4B8
0x18001b4af  test    r8b, r8b
0x18001b4b2  jz      loc_18001B5C0
0x18001b4b8  mov     r9, [rcx+28h]
0x18001b4bc  mov     rcx, [rcx+10h]
0x18001b4c0  mov     [rsp+1E8h+var_1B0], r12
0x18001b4c5  mov     word ptr [rsp+1E8h+lpNumberOfBytesTransferred], 0Eh
0x18001b4cc  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b4d1  jmp     loc_18001B5B9
0x18001b4d6  call    ?MonitorAutoConfigService@@YAXXZ; MonitorAutoConfigService(void)
0x18001b4db  jmp     loc_18001B5B9
0x18001b4e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4e7  cmp     rcx, rbp
0x18001b4ea  jz      short loc_18001B4F7
0x18001b4ec  cmp     byte ptr [rcx+19h], 3
0x18001b4f0  jb      short loc_18001B4F7
0x18001b4f2  mov     dl, sil
0x18001b4f5  jmp     short loc_18001B4F9
0x18001b4f7  xor     dl, dl
0x18001b4f9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001b500  setnz   r8b
0x18001b504  test    dl, dl
0x18001b506  jnz     short loc_18001B50D
0x18001b508  test    r8b, r8b
0x18001b50b  jz      short loc_18001B579
0x18001b50d  mov     r9, [rcx+28h]
0x18001b511  mov     rcx, [rcx+10h]
0x18001b515  mov     [rsp+1E8h+var_1A0], eax
0x18001b519  mov     [rsp+1E8h+var_1B0], r12
0x18001b51e  mov     word ptr [rsp+1E8h+lpNumberOfBytesTransferred], 0Bh
0x18001b525  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001b52a  jmp     short loc_18001B572
0x18001b52c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b533  cmp     rcx, rbp
0x18001b536  jz      short loc_18001B543
0x18001b538  cmp     byte ptr [rcx+19h], 4
0x18001b53c  jb      short loc_18001B543
0x18001b53e  mov     dl, sil
0x18001b541  jmp     short loc_18001B545
0x18001b543  xor     dl, dl
0x18001b545  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001b54c  setnz   r8b
0x18001b550  test    dl, dl
0x18001b552  jnz     short loc_18001B559
0x18001b554  test    r8b, r8b
0x18001b557  jz      short loc_18001B579
0x18001b559  mov     r9, [rcx+28h]
0x18001b55d  mov     rcx, [rcx+10h]
0x18001b561  mov     [rsp+1E8h+var_1B0], r12
0x18001b566  mov     word ptr [rsp+1E8h+lpNumberOfBytesTransferred], 0Ch
0x18001b56d  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b572  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b579  mov     rdi, [rsp+1E8h+var_188]
0x18001b57e  test    rdi, rdi
0x18001b581  jz      short loc_18001B5C0
0x18001b583  or      ebx, 0FFFFFFFFh
0x18001b586  mov     eax, ebx
0x18001b588  lock xadd [rdi+8], eax
0x18001b58d  add     eax, ebx
0x18001b58f  jnz     short loc_18001B5B9
0x18001b591  mov     rax, [rdi]
0x18001b594  mov     rcx, rdi
0x18001b597  mov     rax, [rax]
0x18001b59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b59f  mov     eax, ebx
0x18001b5a1  lock xadd [rdi+0Ch], eax
0x18001b5a6  add     eax, ebx
0x18001b5a8  jnz     short loc_18001B5B9
0x18001b5aa  mov     rax, [rdi]
0x18001b5ad  mov     rcx, rdi
0x18001b5b0  mov     rax, [rax+8]
0x18001b5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b5c0  cmp     rcx, rbp
0x18001b5c3  jz      short loc_18001B5CB
0x18001b5c5  cmp     byte ptr [rcx+19h], 4
0x18001b5c9  jnb     short loc_18001B5CE
0x18001b5cb  xor     sil, sil
0x18001b5ce  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001b5d5  setnz   r8b
0x18001b5d9  test    sil, sil
0x18001b5dc  jnz     short loc_18001B5E3
0x18001b5de  test    r8b, r8b
0x18001b5e1  jz      short loc_18001B5FF
0x18001b5e3  mov     r9, [rcx+28h]
0x18001b5e7  mov     dl, sil
0x18001b5ea  mov     rcx, [rcx+10h]
0x18001b5ee  mov     [rsp+1E8h+var_1B0], r12
0x18001b5f3  mov     word ptr [rsp+1E8h+lpNumberOfBytesTransferred], 0Fh
0x18001b5fa  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b5ff  mov     rcx, [rsp+1E8h+var_48]
0x18001b607  xor     rcx, rsp; StackCookie
0x18001b60a  call    __security_check_cookie
0x18001b60f  add     rsp, 1B8h
0x18001b616  pop     r14
0x18001b618  pop     r12
0x18001b61a  pop     rdi
0x18001b61b  pop     rsi
0x18001b61c  pop     rbp
0x18001b61d  pop     rbx
0x18001b61e  retn
```
