# CSusSecurityChecker::~CSusSecurityChecker(void)

- ea: `0x18000dee8`
- end: `0x18000dfec`
- name: `??1CSusSecurityChecker@@QEAA@XZ`
- size: `260`
- prototype: `void __fastcall(CSusSecurityChecker *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018124`
- `0x180019024`
- `0x18006a0f3`
- `0x18006a14d`

## callees

- `0x18000dee8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dfca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dfca`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000defe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df15`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df2c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df43`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df5a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df71`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df88`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df9f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000dfb6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000defe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df15`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df2c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df43`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df5a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df71`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df88`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000df9f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000dfb6`

## pseudocode

```c
void __fastcall CSusSecurityChecker::~CSusSecurityChecker(CSusSecurityChecker *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  __int64 i; // rdi

  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
    FreeSid(v2);
  *((_QWORD *)this + 8) = 0;
  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
    FreeSid(v3);
  *((_QWORD *)this + 9) = 0;
  v4 = (void *)*((_QWORD *)this + 10);
  if ( v4 )
    FreeSid(v4);
  *((_QWORD *)this + 10) = 0;
  v5 = (void *)*((_QWORD *)this + 6);
  if ( v5 )
    FreeSid(v5);
  *((_QWORD *)this + 6) = 0;
  v6 = (void *)*((_QWORD *)this + 7);
  if ( v6 )
    FreeSid(v6);
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 11);
  if ( v7 )
    FreeSid(v7);
  *((_QWORD *)this + 11) = 0;
  v8 = (void *)*((_QWORD *)this + 5);
  if ( v8 )
    FreeSid(v8);
  *((_QWORD *)this + 5) = 0;
  v9 = (void *)*((_QWORD *)this + 12);
  if ( v9 )
    FreeSid(v9);
  *((_QWORD *)this + 12) = 0;
  v10 = (void *)*((_QWORD *)this + 13);
  if ( v10 )
    FreeSid(v10);
  *((_QWORD *)this + 13) = 0;
  for ( i = 0; i < 5; ++i )
  {
    LocalFree(*((HLOCAL *)this + i));
    *((_QWORD *)this + i) = 0;
  }
}

```

## disassembly

```asm
0x18000dee8  mov     [rsp+arg_0], rbx
0x18000deed  push    rdi
0x18000deee  sub     rsp, 20h
0x18000def2  mov     rbx, rcx
0x18000def5  mov     rcx, [rcx+40h]; pSid
0x18000def9  test    rcx, rcx
0x18000defc  jz      short loc_18000DF04
0x18000defe  call    cs:__imp_FreeSid
0x18000df04  mov     qword ptr [rbx+40h], 0
0x18000df0c  mov     rcx, [rbx+48h]; pSid
0x18000df10  test    rcx, rcx
0x18000df13  jz      short loc_18000DF1B
0x18000df15  call    cs:__imp_FreeSid
0x18000df1b  mov     qword ptr [rbx+48h], 0
0x18000df23  mov     rcx, [rbx+50h]; pSid
0x18000df27  test    rcx, rcx
0x18000df2a  jz      short loc_18000DF32
0x18000df2c  call    cs:__imp_FreeSid
0x18000df32  mov     qword ptr [rbx+50h], 0
0x18000df3a  mov     rcx, [rbx+30h]; pSid
0x18000df3e  test    rcx, rcx
0x18000df41  jz      short loc_18000DF49
0x18000df43  call    cs:__imp_FreeSid
0x18000df49  mov     qword ptr [rbx+30h], 0
0x18000df51  mov     rcx, [rbx+38h]; pSid
0x18000df55  test    rcx, rcx
0x18000df58  jz      short loc_18000DF60
0x18000df5a  call    cs:__imp_FreeSid
0x18000df60  mov     qword ptr [rbx+38h], 0
0x18000df68  mov     rcx, [rbx+58h]; pSid
0x18000df6c  test    rcx, rcx
0x18000df6f  jz      short loc_18000DF77
0x18000df71  call    cs:__imp_FreeSid
0x18000df77  mov     qword ptr [rbx+58h], 0
0x18000df7f  mov     rcx, [rbx+28h]; pSid
0x18000df83  test    rcx, rcx
0x18000df86  jz      short loc_18000DF8E
0x18000df88  call    cs:__imp_FreeSid
0x18000df8e  mov     qword ptr [rbx+28h], 0
0x18000df96  mov     rcx, [rbx+60h]; pSid
0x18000df9a  test    rcx, rcx
0x18000df9d  jz      short loc_18000DFA5
0x18000df9f  call    cs:__imp_FreeSid
0x18000dfa5  mov     qword ptr [rbx+60h], 0
0x18000dfad  mov     rcx, [rbx+68h]; pSid
0x18000dfb1  test    rcx, rcx
0x18000dfb4  jz      short loc_18000DFBC
0x18000dfb6  call    cs:__imp_FreeSid
0x18000dfbc  mov     qword ptr [rbx+68h], 0
0x18000dfc4  xor     edi, edi
0x18000dfc6  mov     rcx, [rbx+rdi*8]; hMem
0x18000dfca  call    cs:__imp_LocalFree
0x18000dfd0  mov     qword ptr [rbx+rdi*8], 0
0x18000dfd8  inc     rdi
0x18000dfdb  cmp     rdi, 5
0x18000dfdf  jl      short loc_18000DFC6
0x18000dfe1  mov     rbx, [rsp+28h+arg_0]
0x18000dfe6  add     rsp, 20h
0x18000dfea  pop     rdi
0x18000dfeb  retn
```
