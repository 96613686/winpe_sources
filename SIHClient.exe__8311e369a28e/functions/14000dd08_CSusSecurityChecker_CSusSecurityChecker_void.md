# CSusSecurityChecker::~CSusSecurityChecker(void)

- ea: `0x14000dd08`
- end: `0x14000de0c`
- name: `??1CSusSecurityChecker@@QEAA@XZ`
- size: `260`
- prototype: `void __fastcall(CSusSecurityChecker *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003ee0`

## callees

- `0x14000dd08`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd1e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd35`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd4c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd63`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd7a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd91`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dda8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000ddbf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000ddd6`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd1e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd35`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd4c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd63`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd7a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dd91`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000dda8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000ddbf`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x14000ddd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000ddea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000ddea`

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
0x14000dd08  mov     [rsp+arg_0], rbx
0x14000dd0d  push    rdi
0x14000dd0e  sub     rsp, 20h
0x14000dd12  mov     rbx, rcx
0x14000dd15  mov     rcx, [rcx+40h]; pSid
0x14000dd19  test    rcx, rcx
0x14000dd1c  jz      short loc_14000DD24
0x14000dd1e  call    cs:__imp_FreeSid
0x14000dd24  mov     qword ptr [rbx+40h], 0
0x14000dd2c  mov     rcx, [rbx+48h]; pSid
0x14000dd30  test    rcx, rcx
0x14000dd33  jz      short loc_14000DD3B
0x14000dd35  call    cs:__imp_FreeSid
0x14000dd3b  mov     qword ptr [rbx+48h], 0
0x14000dd43  mov     rcx, [rbx+50h]; pSid
0x14000dd47  test    rcx, rcx
0x14000dd4a  jz      short loc_14000DD52
0x14000dd4c  call    cs:__imp_FreeSid
0x14000dd52  mov     qword ptr [rbx+50h], 0
0x14000dd5a  mov     rcx, [rbx+30h]; pSid
0x14000dd5e  test    rcx, rcx
0x14000dd61  jz      short loc_14000DD69
0x14000dd63  call    cs:__imp_FreeSid
0x14000dd69  mov     qword ptr [rbx+30h], 0
0x14000dd71  mov     rcx, [rbx+38h]; pSid
0x14000dd75  test    rcx, rcx
0x14000dd78  jz      short loc_14000DD80
0x14000dd7a  call    cs:__imp_FreeSid
0x14000dd80  mov     qword ptr [rbx+38h], 0
0x14000dd88  mov     rcx, [rbx+58h]; pSid
0x14000dd8c  test    rcx, rcx
0x14000dd8f  jz      short loc_14000DD97
0x14000dd91  call    cs:__imp_FreeSid
0x14000dd97  mov     qword ptr [rbx+58h], 0
0x14000dd9f  mov     rcx, [rbx+28h]; pSid
0x14000dda3  test    rcx, rcx
0x14000dda6  jz      short loc_14000DDAE
0x14000dda8  call    cs:__imp_FreeSid
0x14000ddae  mov     qword ptr [rbx+28h], 0
0x14000ddb6  mov     rcx, [rbx+60h]; pSid
0x14000ddba  test    rcx, rcx
0x14000ddbd  jz      short loc_14000DDC5
0x14000ddbf  call    cs:__imp_FreeSid
0x14000ddc5  mov     qword ptr [rbx+60h], 0
0x14000ddcd  mov     rcx, [rbx+68h]; pSid
0x14000ddd1  test    rcx, rcx
0x14000ddd4  jz      short loc_14000DDDC
0x14000ddd6  call    cs:__imp_FreeSid
0x14000dddc  mov     qword ptr [rbx+68h], 0
0x14000dde4  xor     edi, edi
0x14000dde6  mov     rcx, [rbx+rdi*8]; hMem
0x14000ddea  call    cs:__imp_LocalFree
0x14000ddf0  mov     qword ptr [rbx+rdi*8], 0
0x14000ddf8  inc     rdi
0x14000ddfb  cmp     rdi, 5
0x14000ddff  jl      short loc_14000DDE6
0x14000de01  mov     rbx, [rsp+28h+arg_0]
0x14000de06  add     rsp, 20h
0x14000de0a  pop     rdi
0x14000de0b  retn
```
