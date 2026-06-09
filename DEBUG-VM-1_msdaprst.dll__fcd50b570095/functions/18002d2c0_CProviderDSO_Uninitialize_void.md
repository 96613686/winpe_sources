# CProviderDSO::Uninitialize(void)

- ea: `0x18002d2c0`
- end: `0x18002d409`
- name: `?Uninitialize@CProviderDSO@@UEAAJXZ`
- size: `329`
- prototype: `__int64 __fastcall(CProviderDSO *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001a6c8`
- `0x18002cd54`
- `0x18002d2c0`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002d2f4`
- `KERNEL32!GetCurrentThreadId` at `0x18002d2f4`
- `KERNEL32!LeaveCriticalSection` at `0x18002d3bb`
- `KERNEL32!LeaveCriticalSection` at `0x18002d3f2`
- `KERNEL32!LeaveCriticalSection` at `0x18002d3bb`
- `KERNEL32!LeaveCriticalSection` at `0x18002d3f2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002d316`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002d316`
- `MSDART!UMSEnterCSWraper` at `0x18002d2e0`
- `MSDART!UMSEnterCSWraper` at `0x18002d2e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProviderDSO::Uninitialize(CProviderDSO *this)
{
  char *v2; // rbx
  _DWORD *v3; // rdi
  bool v4; // zf
  __int64 v5; // rcx
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  _BYTE *v12; // rdx
  _BYTE *v13; // rdx
  _BYTE v14[32]; // [rsp+0h] [rbp-78h] BYREF
  __int64 v15; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *v16; // [rsp+38h] [rbp-40h]
  char *v17; // [rsp+40h] [rbp-38h]
  __int64 v18; // [rsp+80h] [rbp+8h]
  __int64 v19; // [rsp+90h] [rbp+18h]
  _DWORD *v20; // [rsp+98h] [rbp+20h]

  v2 = (char *)this + 56;
  UMSEnterCSWraper((char *)this + 56);
  v3 = v2 + 12;
  v16 = v2 + 12;
  if ( !*((_DWORD *)v2 + 3) )
    *((_DWORD *)v2 + 2) = GetCurrentThreadId();
  ++*v3;
  ++*((_DWORD *)v2 + 4);
  v17 = v2;
  SetErrorInfo(0, 0);
  *(GUID *)((char *)this + 104) = IID_IDBInitialize;
  *((_DWORD *)this + 1055) = 0;
  if ( *((_DWORD *)this + 12) )
  {
    if ( (bidGblFlags & 2) != 0 && off_180048EF0[0] )
      bidTraceW(off_180048228[0], 159744, off_180048EF0[0], 2147749381LL, 156);
    try
    {
      ThrowHR(-2147217915);
    }
    catch ( long v15 )
    {
      v12 = v14;
      *((_DWORD *)v12 + 32) = CError::PostErrorIfNone(
                                (CError *)(*((_QWORD *)v12 + 16) + 88LL),
                                *((_DWORD *)v12 + 12),
                                v10);
      goto LABEL_10;
    }
    catch ( ... )
    {
      v13 = v14;
      *((_DWORD *)v13 + 32) = CError::PostErrorIfNone((CError *)(*((_QWORD *)v13 + 16) + 88LL), -2147467259, v11);
LABEL_10:
      v7 = -1;
      --*v20;
      v4 = (*v16)-- == 1;
      v8 = v19;
      if ( v4 )
        *(_DWORD *)(v8 + 8) = v7;
      v9 = *(_QWORD *)v8;
      --*(_DWORD *)(v9 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
      return (unsigned int)v18;
    }
  }
  (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this - 2) + 32LL))((char *)this - 16, 0);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 2) + 48LL))((char *)this - 16);
  --*((_DWORD *)v2 + 4);
  v4 = (*v3)-- == 1;
  if ( v4 )
    *((_DWORD *)v2 + 2) = -1;
  v5 = *(_QWORD *)v2;
  --*(_DWORD *)(v5 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  return 0;
}

```

## disassembly

```asm
0x18002d2c0  mov     [rsp+arg_0], rcx
0x18002d2c5  push    rbx
0x18002d2c6  push    rsi
0x18002d2c7  push    rdi
0x18002d2c8  push    r14
0x18002d2ca  sub     rsp, 58h
0x18002d2ce  mov     r14, rcx
0x18002d2d1  lea     rbx, [rcx+38h]
0x18002d2d5  mov     [rsp+78h+arg_10], rbx
0x18002d2dd  mov     rcx, rbx
0x18002d2e0  call    cs:__imp_UMSEnterCSWraper
0x18002d2e6  lea     rdi, [rbx+0Ch]
0x18002d2ea  mov     [rsp+78h+var_40], rdi
0x18002d2ef  cmp     dword ptr [rdi], 0
0x18002d2f2  jnz     short loc_18002D2FD
0x18002d2f4  call    cs:__imp_GetCurrentThreadId
0x18002d2fa  mov     [rbx+8], eax
0x18002d2fd  inc     dword ptr [rdi]
0x18002d2ff  lea     rsi, [rbx+10h]
0x18002d303  mov     [rsp+78h+arg_18], rsi
0x18002d30b  inc     dword ptr [rsi]
0x18002d30d  mov     [rsp+78h+var_38], rbx
0x18002d312  xor     edx, edx; perrinfo
0x18002d314  xor     ecx, ecx; dwReserved
0x18002d316  call    cs:__imp_SetErrorInfo
0x18002d31c  movups  xmm0, xmmword ptr cs:IID_IDBInitialize.Data1
0x18002d323  movdqu  xmmword ptr [r14+68h], xmm0
0x18002d329  mov     dword ptr [r14+107Ch], 0
0x18002d334  cmp     dword ptr [r14+30h], 0
0x18002d339  jbe     short loc_18002D380
0x18002d33b  test    byte ptr cs:_bidGblFlags, 2
0x18002d342  jz      short loc_18002D376
0x18002d344  mov     rax, cs:off_180048EF0; "<CProviderDSO::Uninitialize|ADO|ERR>  H"...
0x18002d34b  test    rax, rax
0x18002d34e  jz      short loc_18002D376
0x18002d350  mov     [rsp+78h+var_58], 9Ch
0x18002d358  mov     r9d, 80040E05h
0x18002d35e  mov     r8, cs:off_180048EF0; "<CProviderDSO::Uninitialize|ADO|ERR>  H"...
0x18002d365  mov     edx, 27000h
0x18002d36a  mov     rcx, cs:off_180048228; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002d371  call    _bidTraceW
0x18002d376  mov     ecx, 80040E05h; int
0x18002d37b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002d380  mov     rax, [r14-10h]
0x18002d384  xor     edx, edx
0x18002d386  lea     rcx, [r14-10h]
0x18002d38a  mov     rax, [rax+20h]
0x18002d38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d393  mov     rax, [r14-10h]
0x18002d397  lea     rcx, [r14-10h]
0x18002d39b  mov     rax, [rax+30h]
0x18002d39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3a4  nop
0x18002d3a5  or      ecx, 0FFFFFFFFh
0x18002d3a8  add     [rsi], ecx
0x18002d3aa  add     [rdi], ecx
0x18002d3ac  jnz     short loc_18002D3B1
0x18002d3ae  mov     [rbx+8], ecx
0x18002d3b1  mov     rcx, [rbx]
0x18002d3b4  dec     dword ptr [rcx+30h]
0x18002d3b7  add     rcx, 8; lpCriticalSection
0x18002d3bb  call    cs:__imp_LeaveCriticalSection
0x18002d3c1  xor     eax, eax
0x18002d3c3  jmp     short loc_18002D3FF
0x18002d3c5  jmp     short $+2
0x18002d3c7  mov     rax, [rsp+78h+arg_18]
0x18002d3cf  or      ecx, 0FFFFFFFFh
0x18002d3d2  add     [rax], ecx
0x18002d3d4  mov     rax, [rsp+78h+var_40]
0x18002d3d9  add     [rax], ecx
0x18002d3db  mov     rax, [rsp+78h+arg_10]
0x18002d3e3  jnz     short loc_18002D3E8
0x18002d3e5  mov     [rax+8], ecx
0x18002d3e8  mov     rcx, [rax]
0x18002d3eb  dec     dword ptr [rcx+30h]
0x18002d3ee  add     rcx, 8; lpCriticalSection
0x18002d3f2  call    cs:__imp_LeaveCriticalSection
0x18002d3f8  mov     eax, dword ptr [rsp+78h+arg_0]
0x18002d3ff  add     rsp, 58h
0x18002d403  pop     r14
0x18002d405  pop     rdi
0x18002d406  pop     rsi
0x18002d407  pop     rbx
0x18002d408  retn
```
