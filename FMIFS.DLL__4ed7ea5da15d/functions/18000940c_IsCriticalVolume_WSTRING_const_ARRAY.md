# IsCriticalVolume(WSTRING const *,ARRAY *)

- ea: `0x18000940c`
- end: `0x180009573`
- name: `?IsCriticalVolume@@YAEPEBVWSTRING@@PEAVARRAY@@@Z`
- size: `359`
- prototype: `unsigned __int8 __fastcall(const struct WSTRING *, struct ARRAY *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800015d0`

## callees

- `0x180003bf0`
- `0x18000940c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009453`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800094e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009453`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800094e2`
- `ulib!?Strcmp@WSTRING@@QEBAJPEBV1@@Z` at `0x180009506`
- `ulib!?Strcmp@WSTRING@@QEBAJPEBV1@@Z` at `0x180009506`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180009445`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180009445`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000945e`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000955a`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000945e`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000955a`
- `IfsUtil!?QueryID@DP_DRIVE@@QEAAEPEAVWSTRING@@PEBV2@E@Z` at `0x1800094a1`
- `IfsUtil!?QueryID@DP_DRIVE@@QEAAEPEAVWSTRING@@PEBV2@E@Z` at `0x1800094a1`
- `IfsUtil!??0LOG_IO_DP_DRIVE@@QEAA@XZ` at `0x180009433`
- `IfsUtil!??0LOG_IO_DP_DRIVE@@QEAA@XZ` at `0x180009433`
- `IfsUtil!?Initialize@LOG_IO_DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@E@Z` at `0x180009477`
- `IfsUtil!?Initialize@LOG_IO_DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@E@Z` at `0x180009477`

## pseudocode

```c
char __fastcall IsCriticalVolume(const struct WSTRING *a1, struct ARRAY *a2)
{
  LOG_IO_DP_DRIVE *v4; // rax
  LOG_IO_DP_DRIVE *v5; // rbx
  unsigned __int8 v7; // al
  LOG_IO_DP_DRIVE *v8; // rcx
  char v9; // di
  __int64 v10; // rsi
  const struct WSTRING *v11; // rax
  _BYTE v12[56]; // [rsp+20h] [rbp-38h] BYREF

  v4 = (LOG_IO_DP_DRIVE *)operator new(0x1E0u);
  if ( v4 )
    v5 = LOG_IO_DP_DRIVE::LOG_IO_DP_DRIVE(v4);
  else
    v5 = 0;
  DSTRING::DSTRING((DSTRING *)v12);
  if ( !v5 )
  {
    SetLastError(8u);
LABEL_6:
    DSTRING::~DSTRING((DSTRING *)v12);
    return 0;
  }
  v7 = LOG_IO_DP_DRIVE::Initialize(v5, a1, 0, 0);
  v8 = v5;
  if ( !v7 )
  {
LABEL_8:
    (**(void (__fastcall ***)(LOG_IO_DP_DRIVE *, __int64))v5)(v8, 1);
    goto LABEL_6;
  }
  if ( !DP_DRIVE::QueryID(v5, (struct WSTRING *)v12, 0, 0) )
  {
    v8 = v5;
    goto LABEL_8;
  }
  v9 = 1;
  if ( (*(unsigned int (__fastcall **)(struct ARRAY *))(*(_QWORD *)a2 + 32LL))(a2) )
  {
    v10 = (*(__int64 (__fastcall **)(struct ARRAY *))(*(_QWORD *)a2 + 48LL))(a2);
    if ( v10 )
    {
      while ( 1 )
      {
        v11 = (const struct WSTRING *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 40LL))(v10);
        if ( !v11 )
          break;
        if ( !WSTRING::Strcmp((WSTRING *)v12, v11) )
        {
          (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
          (**(void (__fastcall ***)(LOG_IO_DP_DRIVE *, __int64))v5)(v5, 1);
          goto LABEL_19;
        }
      }
      (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
    }
    else
    {
      SetLastError(8u);
    }
  }
  (**(void (__fastcall ***)(LOG_IO_DP_DRIVE *, __int64))v5)(v5, 1);
  v9 = 0;
LABEL_19:
  DSTRING::~DSTRING((DSTRING *)v12);
  return v9;
}

```

## disassembly

```asm
0x18000940c  mov     [rsp+arg_0], rbx
0x180009411  mov     [rsp+arg_8], rsi
0x180009416  push    rdi
0x180009417  sub     rsp, 50h
0x18000941b  mov     rdi, rcx
0x18000941e  mov     rsi, rdx
0x180009421  mov     ecx, 1E0h; unsigned __int64
0x180009426  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000942b  test    rax, rax
0x18000942e  jz      short loc_18000943E
0x180009430  mov     rcx, rax
0x180009433  call    cs:__imp_??0LOG_IO_DP_DRIVE@@QEAA@XZ; LOG_IO_DP_DRIVE::LOG_IO_DP_DRIVE(void)
0x180009439  mov     rbx, rax
0x18000943c  jmp     short loc_180009440
0x18000943e  xor     ebx, ebx
0x180009440  lea     rcx, [rsp+58h+var_38]
0x180009445  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x18000944b  test    rbx, rbx
0x18000944e  jnz     short loc_18000946B
0x180009450  lea     ecx, [rbx+8]; dwErrCode
0x180009453  call    cs:__imp_SetLastError
0x180009459  lea     rcx, [rsp+58h+var_38]
0x18000945e  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180009464  xor     al, al
0x180009466  jmp     loc_180009563
0x18000946b  xor     r9d, r9d
0x18000946e  xor     r8d, r8d
0x180009471  mov     rdx, rdi
0x180009474  mov     rcx, rbx
0x180009477  call    cs:__imp_?Initialize@LOG_IO_DP_DRIVE@@QEAAEPEBVWSTRING@@PEAVMESSAGE@@E@Z; LOG_IO_DP_DRIVE::Initialize(WSTRING const *,MESSAGE *,uchar)
0x18000947d  mov     rcx, rbx
0x180009480  test    al, al
0x180009482  jnz     short loc_180009496
0x180009484  mov     rax, [rbx]
0x180009487  mov     edx, 1
0x18000948c  mov     rax, [rax]
0x18000948f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009494  jmp     short loc_180009459
0x180009496  xor     r9d, r9d
0x180009499  lea     rdx, [rsp+58h+var_38]
0x18000949e  xor     r8d, r8d
0x1800094a1  call    cs:__imp_?QueryID@DP_DRIVE@@QEAAEPEAVWSTRING@@PEBV2@E@Z; DP_DRIVE::QueryID(WSTRING *,WSTRING const *,uchar)
0x1800094a7  test    al, al
0x1800094a9  jnz     short loc_1800094B0
0x1800094ab  mov     rcx, rbx
0x1800094ae  jmp     short loc_180009484
0x1800094b0  mov     rax, [rsi]
0x1800094b3  mov     rcx, rsi
0x1800094b6  mov     rax, [rax+20h]
0x1800094ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094bf  mov     edi, 1
0x1800094c4  test    eax, eax
0x1800094c6  jz      short loc_180009542
0x1800094c8  mov     rax, [rsi]
0x1800094cb  mov     rcx, rsi
0x1800094ce  mov     rax, [rax+30h]
0x1800094d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d7  mov     rsi, rax
0x1800094da  test    rax, rax
0x1800094dd  jnz     short loc_1800094EA
0x1800094df  lea     ecx, [rdi+7]; dwErrCode
0x1800094e2  call    cs:__imp_SetLastError
0x1800094e8  jmp     short loc_180009542
0x1800094ea  mov     rax, [rsi]
0x1800094ed  mov     rcx, rsi
0x1800094f0  mov     rax, [rax+28h]
0x1800094f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f9  test    rax, rax
0x1800094fc  jz      short loc_180009532
0x1800094fe  mov     rdx, rax
0x180009501  lea     rcx, [rsp+58h+var_38]
0x180009506  call    cs:__imp_?Strcmp@WSTRING@@QEBAJPEBV1@@Z; WSTRING::Strcmp(WSTRING const *)
0x18000950c  test    eax, eax
0x18000950e  jnz     short loc_1800094EA
0x180009510  mov     rax, [rsi]
0x180009513  mov     edx, edi
0x180009515  mov     rcx, rsi
0x180009518  mov     rax, [rax]
0x18000951b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009520  mov     rax, [rbx]
0x180009523  mov     edx, edi
0x180009525  mov     rcx, rbx
0x180009528  mov     rax, [rax]
0x18000952b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009530  jmp     short loc_180009555
0x180009532  mov     rax, [rsi]
0x180009535  mov     edx, edi
0x180009537  mov     rcx, rsi
0x18000953a  mov     rax, [rax]
0x18000953d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009542  mov     rax, [rbx]
0x180009545  mov     edx, edi
0x180009547  mov     rcx, rbx
0x18000954a  mov     rax, [rax]
0x18000954d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009552  xor     dil, dil
0x180009555  lea     rcx, [rsp+58h+var_38]
0x18000955a  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180009560  mov     al, dil
0x180009563  mov     rbx, [rsp+58h+arg_0]
0x180009568  mov     rsi, [rsp+58h+arg_8]
0x18000956d  add     rsp, 50h
0x180009571  pop     rdi
0x180009572  retn
```
