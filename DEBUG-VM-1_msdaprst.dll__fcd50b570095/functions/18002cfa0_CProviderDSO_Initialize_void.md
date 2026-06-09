# CProviderDSO::Initialize(void)

- ea: `0x18002cfa0`
- end: `0x18002d0ec`
- name: `?Initialize@CProviderDSO@@UEAAJXZ`
- size: `332`
- prototype: `__int64 __fastcall(CProviderDSO *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001a6c8`
- `0x18002cd54`
- `0x18002cfa0`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002cfd4`
- `KERNEL32!GetCurrentThreadId` at `0x18002cfd4`
- `KERNEL32!LeaveCriticalSection` at `0x18002d09e`
- `KERNEL32!LeaveCriticalSection` at `0x18002d0d5`
- `KERNEL32!LeaveCriticalSection` at `0x18002d09e`
- `KERNEL32!LeaveCriticalSection` at `0x18002d0d5`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002cff6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002cff6`
- `MSDART!UMSEnterCSWraper` at `0x18002cfc0`
- `MSDART!UMSEnterCSWraper` at `0x18002cfc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProviderDSO::Initialize(CProviderDSO *this)
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
  if ( *((_DWORD *)this + 20) )
  {
    if ( (bidGblFlags & 2) != 0 && off_180048EE8[0] )
      bidTraceW(off_180048228[0], 126976, off_180048EE8[0], 2147749458LL, 124);
    try
    {
      ThrowHR(-2147217838);
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
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 2) + 40LL))((char *)this - 16);
  (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this - 2) + 32LL))((char *)this - 16, 1);
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
0x18002cfa0  mov     [rsp+arg_0], rcx
0x18002cfa5  push    rbx
0x18002cfa6  push    rsi
0x18002cfa7  push    rdi
0x18002cfa8  push    r14
0x18002cfaa  sub     rsp, 58h
0x18002cfae  mov     r14, rcx
0x18002cfb1  lea     rbx, [rcx+38h]
0x18002cfb5  mov     [rsp+78h+arg_10], rbx
0x18002cfbd  mov     rcx, rbx
0x18002cfc0  call    cs:__imp_UMSEnterCSWraper
0x18002cfc6  lea     rdi, [rbx+0Ch]
0x18002cfca  mov     [rsp+78h+var_40], rdi
0x18002cfcf  cmp     dword ptr [rdi], 0
0x18002cfd2  jnz     short loc_18002CFDD
0x18002cfd4  call    cs:__imp_GetCurrentThreadId
0x18002cfda  mov     [rbx+8], eax
0x18002cfdd  inc     dword ptr [rdi]
0x18002cfdf  lea     rsi, [rbx+10h]
0x18002cfe3  mov     [rsp+78h+arg_18], rsi
0x18002cfeb  inc     dword ptr [rsi]
0x18002cfed  mov     [rsp+78h+var_38], rbx
0x18002cff2  xor     edx, edx; perrinfo
0x18002cff4  xor     ecx, ecx; dwReserved
0x18002cff6  call    cs:__imp_SetErrorInfo
0x18002cffc  movups  xmm0, xmmword ptr cs:IID_IDBInitialize.Data1
0x18002d003  movdqu  xmmword ptr [r14+68h], xmm0
0x18002d009  mov     dword ptr [r14+107Ch], 0
0x18002d014  cmp     dword ptr [r14+50h], 0
0x18002d019  jz      short loc_18002D060
0x18002d01b  test    byte ptr cs:_bidGblFlags, 2
0x18002d022  jz      short loc_18002D056
0x18002d024  mov     rax, cs:off_180048EE8; "<CProviderDSO::Initialize|ADO|ERR>  HRE"...
0x18002d02b  test    rax, rax
0x18002d02e  jz      short loc_18002D056
0x18002d030  mov     [rsp+78h+var_58], 7Ch ; '|'
0x18002d038  mov     r9d, 80040E52h
0x18002d03e  mov     r8, cs:off_180048EE8; "<CProviderDSO::Initialize|ADO|ERR>  HRE"...
0x18002d045  mov     edx, 1F000h
0x18002d04a  mov     rcx, cs:off_180048228; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002d051  call    _bidTraceW
0x18002d056  mov     ecx, 80040E52h; int
0x18002d05b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002d060  mov     rax, [r14-10h]
0x18002d064  lea     rcx, [r14-10h]
0x18002d068  mov     rax, [rax+28h]
0x18002d06c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d071  mov     rax, [r14-10h]
0x18002d075  mov     edx, 1
0x18002d07a  lea     rcx, [r14-10h]
0x18002d07e  mov     rax, [rax+20h]
0x18002d082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d087  nop
0x18002d088  or      ecx, 0FFFFFFFFh
0x18002d08b  add     [rsi], ecx
0x18002d08d  add     [rdi], ecx
0x18002d08f  jnz     short loc_18002D094
0x18002d091  mov     [rbx+8], ecx
0x18002d094  mov     rcx, [rbx]
0x18002d097  dec     dword ptr [rcx+30h]
0x18002d09a  add     rcx, 8; lpCriticalSection
0x18002d09e  call    cs:__imp_LeaveCriticalSection
0x18002d0a4  xor     eax, eax
0x18002d0a6  jmp     short loc_18002D0E2
0x18002d0a8  jmp     short $+2
0x18002d0aa  mov     rax, [rsp+78h+arg_18]
0x18002d0b2  or      ecx, 0FFFFFFFFh
0x18002d0b5  add     [rax], ecx
0x18002d0b7  mov     rax, [rsp+78h+var_40]
0x18002d0bc  add     [rax], ecx
0x18002d0be  mov     rax, [rsp+78h+arg_10]
0x18002d0c6  jnz     short loc_18002D0CB
0x18002d0c8  mov     [rax+8], ecx
0x18002d0cb  mov     rcx, [rax]
0x18002d0ce  dec     dword ptr [rcx+30h]
0x18002d0d1  add     rcx, 8; lpCriticalSection
0x18002d0d5  call    cs:__imp_LeaveCriticalSection
0x18002d0db  mov     eax, dword ptr [rsp+78h+arg_0]
0x18002d0e2  add     rsp, 58h
0x18002d0e6  pop     r14
0x18002d0e8  pop     rdi
0x18002d0e9  pop     rsi
0x18002d0ea  pop     rbx
0x18002d0eb  retn
```
