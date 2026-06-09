# CRegistrySearch::LocateKeyByNameOrValueName(HKEY__ *,ushort const *,ushort const *,ushort const * *,ulong,CHString &,CHString &)

- ea: `0x140012f60`
- end: `0x140013179`
- name: `?LocateKeyByNameOrValueName@CRegistrySearch@@QEAAHPEAUHKEY__@@PEBG1PEAPEBGKAEAVCHString@@3@Z`
- size: `537`
- prototype: `__int64 __fastcall(CRegistrySearch *this, HKEY, const unsigned __int16 *, char *, const unsigned __int16 **, unsigned int, struct CHString *, struct CHString *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x140012f60`

## callees

- `0x14000fc80`
- `0x14000ff40`
- `0x14000ffc0`
- `0x140010cd0`
- `0x140011be0`
- `0x140011cc0`
- `0x140012040`
- `0x140012c70`
- `0x140012ea0`
- `0x140012f60`
- `0x140013180`
- `0x1400131d0`
- `0x140014ad0`

## pseudocode

```c
__int64 __fastcall CRegistrySearch::LocateKeyByNameOrValueName(
        CRegistrySearch *this,
        HKEY a2,
        const unsigned __int16 *a3,
        char *a4,
        const unsigned __int16 **a5,
        unsigned int a6,
        struct CHString *a7,
        struct CHString *a8)
{
  const unsigned __int16 *v9; // rsi
  __int64 result; // rax
  unsigned int KeyByNameOrValueName; // edi
  int v13; // eax
  unsigned __int16 *v14; // rbx
  unsigned __int16 *v15; // rax
  int v16; // edx
  int v17; // ecx
  __int64 i; // rsi
  unsigned __int16 *v19; // [rsp+40h] [rbp-2D8h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-2D0h] BYREF
  const unsigned __int16 *v21; // [rsp+50h] [rbp-2C8h]
  CHString *v22; // [rsp+58h] [rbp-2C0h]
  const unsigned __int16 *v23; // [rsp+60h] [rbp-2B8h] BYREF
  CRegistrySearch *v24; // [rsp+68h] [rbp-2B0h]
  _BYTE v25[8]; // [rsp+70h] [rbp-2A8h] BYREF
  HKEY v26; // [rsp+78h] [rbp-2A0h]

  v9 = a3;
  v21 = a3;
  v24 = this;
  v22 = a7;
  CRegistry::CRegistry((CRegistry *)v25);
  if ( a4 || a5 )
  {
    KeyByNameOrValueName = 0;
    v13 = ((int (__stdcall *)(CRegistry *, HKEY, const unsigned __int16 *, unsigned int))CRegistry::Open)(
            (CRegistry *)v25,
            a2,
            v9,
            0x20019u);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      if ( !v13 )
      {
        v19 = (unsigned __int16 *)afxPchNil;
        v20 = 0;
        while ( !KeyByNameOrValueName
             && !(unsigned int)CRegistry::GetCurrentSubKeyName((CRegistry *)v25, (struct CHString *)&v19) )
        {
          v14 = v19;
          if ( !a4 )
            goto LABEL_15;
          v15 = v19;
          do
          {
            v16 = *(unsigned __int16 *)((char *)v15 + a4 - (char *)v19);
            v17 = *v15 - v16;
            if ( v17 )
              break;
            ++v15;
          }
          while ( v16 );
          if ( v17 )
          {
LABEL_15:
            if ( a5 )
            {
              for ( i = 0; ; i = (unsigned int)(i + 1) )
              {
                if ( KeyByNameOrValueName )
                {
                  v9 = v21;
                  goto LABEL_21;
                }
                if ( (unsigned int)i >= a6 )
                  break;
                KeyByNameOrValueName = CRegistry::GetCurrentSubKeyValue((CRegistry *)v25, a5[i], 0, &v20) == 0;
              }
              v9 = v21;
            }
            KeyByNameOrValueName = CRegistrySearch::LocateKeyByNameOrValueName(v24, v26, v14, a4, a5, a6, v22, a8);
          }
          else
          {
            KeyByNameOrValueName = 1;
LABEL_21:
            CHString::operator=((const unsigned __int16 **)v22, (const unsigned __int16 **)&v19);
            CHString::operator=((const unsigned __int16 **)a8, (const unsigned __int16 **)&v19);
          }
          if ( KeyByNameOrValueName )
          {
            CHString::CHString((CHString *)&v23, (unsigned __int16 **)a8);
            CHString::Format(a8, L"%s\\%s", v9, v23);
            CHString::~CHString(&v23);
          }
          else
          {
            CRegistry::NextSubKey((CRegistry *)v25);
          }
        }
        CRegistry::Close((CRegistry *)v25);
        CHString::~CHString((const unsigned __int16 **)&v19);
      }
      CRegistry::~CRegistry((CRegistry *)v25);
      result = KeyByNameOrValueName;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &CHeap_Exception `RTTI Type Descriptor', 0) )
      {
        CRegistry::Close((CRegistry *)v25);
        throw;
      }
    }
  }
  else
  {
    CRegistry::~CRegistry((CRegistry *)v25);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140012f60  push    rbx
0x140012f62  push    rsi
0x140012f63  push    rdi
0x140012f64  push    r12
0x140012f66  push    r13
0x140012f68  push    r14
0x140012f6a  push    r15
0x140012f6c  sub     rsp, 2E0h
0x140012f73  mov     rax, cs:__security_cookie
0x140012f7a  xor     rax, rsp
0x140012f7d  mov     [rsp+318h+var_48], rax
0x140012f85  mov     r12, r9
0x140012f88  mov     rsi, r8
0x140012f8b  mov     [rsp+318h+var_2C8], r8
0x140012f90  mov     rbx, rdx
0x140012f93  mov     [rsp+318h+var_2B0], rcx
0x140012f98  mov     r14, [rsp+318h+arg_20]
0x140012fa0  mov     rax, [rsp+318h+arg_30]
0x140012fa8  mov     [rsp+318h+var_2C0], rax
0x140012fad  mov     r15, [rsp+318h+arg_38]
0x140012fb5  lea     rcx, [rsp+318h+var_2A8]; this
0x140012fba  call    ??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x140012fbf  nop
0x140012fc0  test    r12, r12
0x140012fc3  jnz     short loc_140012FDB
0x140012fc5  test    r14, r14
0x140012fc8  jnz     short loc_140012FDB
0x140012fca  lea     rcx, [rsp+318h+var_2A8]; this
0x140012fcf  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x140012fd4  xor     eax, eax
0x140012fd6  jmp     loc_140013156
0x140012fdb  xor     edi, edi
0x140012fdd  mov     r9d, 20019h; unsigned int
0x140012fe3  mov     r8, rsi; unsigned __int16 *
0x140012fe6  mov     rdx, rbx; HKEY
0x140012fe9  lea     rcx, [rsp+318h+var_2A8]; this
0x140012fee  call    ?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x140012ff3  test    eax, eax
0x140012ff5  jnz     loc_14001314A
0x140012ffb  mov     rax, cs:?afxPchNil@@3PEBGEB; ushort const * const afxPchNil
0x140013002  mov     [rsp+318h+var_2D8], rax
0x140013007  mov     [rsp+318h+var_2D0], edi
0x14001300b  mov     r13d, [rsp+318h+arg_28]
0x140013013  test    edi, edi
0x140013015  jnz     loc_140013134
0x14001301b  lea     rdx, [rsp+318h+var_2D8]; struct CHString *
0x140013020  lea     rcx, [rsp+318h+var_2A8]; this
0x140013025  call    ?GetCurrentSubKeyName@CRegistry@@QEAAKAEAVCHString@@@Z; CRegistry::GetCurrentSubKeyName(CHString &)
0x14001302a  test    eax, eax
0x14001302c  jnz     loc_140013134
0x140013032  mov     rbx, [rsp+318h+var_2D8]
0x140013037  test    r12, r12
0x14001303a  jz      short loc_140013062
0x14001303c  mov     rax, rbx
0x14001303f  mov     r8, r12
0x140013042  sub     r8, rbx
0x140013045  movzx   ecx, word ptr [rax]
0x140013048  movzx   edx, word ptr [rax+r8]
0x14001304d  sub     ecx, edx
0x14001304f  jnz     short loc_140013059
0x140013051  add     rax, 2
0x140013055  test    edx, edx
0x140013057  jnz     short loc_140013045
0x140013059  test    ecx, ecx
0x14001305b  jnz     short loc_140013062
0x14001305d  lea     edi, [rcx+1]
0x140013060  jmp     short loc_140013099
0x140013062  test    r14, r14
0x140013065  jz      short loc_1400130BC
0x140013067  xor     esi, esi
0x140013069  test    edi, edi
0x14001306b  jnz     short loc_140013094
0x14001306d  cmp     esi, r13d
0x140013070  jnb     short loc_1400130B7
0x140013072  lea     r9, [rsp+318h+var_2D0]; unsigned int *
0x140013077  xor     r8d, r8d; void *
0x14001307a  mov     rdx, [r14+rsi*8]; unsigned __int16 *
0x14001307e  lea     rcx, [rsp+318h+var_2A8]; this
0x140013083  call    ?GetCurrentSubKeyValue@CRegistry@@QEAAKPEBGPEAXPEAK@Z; CRegistry::GetCurrentSubKeyValue(ushort const *,void *,ulong *)
0x140013088  test    eax, eax
0x14001308a  lea     eax, [rdi+1]
0x14001308d  cmovz   edi, eax
0x140013090  add     esi, eax
0x140013092  jmp     short loc_140013069
0x140013094  mov     rsi, [rsp+318h+var_2C8]
0x140013099  lea     rdx, [rsp+318h+var_2D8]
0x14001309e  mov     rcx, [rsp+318h+var_2C0]; this
0x1400130a3  call    ??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x1400130a8  lea     rdx, [rsp+318h+var_2D8]
0x1400130ad  mov     rcx, r15; this
0x1400130b0  call    ??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x1400130b5  jmp     short loc_1400130EC
0x1400130b7  mov     rsi, [rsp+318h+var_2C8]
0x1400130bc  mov     [rsp+318h+var_2E0], r15; struct CHString *
0x1400130c1  mov     rax, [rsp+318h+var_2C0]
0x1400130c6  mov     [rsp+318h+var_2E8], rax; struct CHString *
0x1400130cb  mov     [rsp+318h+var_2F0], r13d; unsigned int
0x1400130d0  mov     [rsp+318h+var_2F8], r14; unsigned __int16 **
0x1400130d5  mov     r9, r12; unsigned __int16 *
0x1400130d8  mov     r8, rbx; unsigned __int16 *
0x1400130db  mov     rdx, [rsp+318h+var_2A0]; HKEY
0x1400130e0  mov     rcx, [rsp+318h+var_2B0]; this
0x1400130e5  call    ?LocateKeyByNameOrValueName@CRegistrySearch@@QEAAHPEAUHKEY__@@PEBG1PEAPEBGKAEAVCHString@@3@Z; CRegistrySearch::LocateKeyByNameOrValueName(HKEY__ *,ushort const *,ushort const *,ushort const * *,ulong,CHString &,CHString &)
0x1400130ea  mov     edi, eax
0x1400130ec  test    edi, edi
0x1400130ee  jz      short loc_140013125
0x1400130f0  mov     rdx, r15; struct CHString *
0x1400130f3  lea     rcx, [rsp+318h+var_2B8]; this
0x1400130f8  call    ??0CHString@@QEAA@AEBV0@@Z; CHString::CHString(CHString const &)
0x1400130fd  nop
0x1400130fe  mov     r9, [rsp+318h+var_2B8]
0x140013103  mov     r8, rsi
0x140013106  lea     rdx, aSS; "%s\\%s"
0x14001310d  mov     rcx, r15; this
0x140013110  call    ?Format@CHString@@QEAAXPEBGZZ; CHString::Format(ushort const *,...)
0x140013115  nop
0x140013116  lea     rcx, [rsp+318h+var_2B8]; this
0x14001311b  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013120  jmp     loc_140013013
0x140013125  lea     rcx, [rsp+318h+var_2A8]; this
0x14001312a  call    ?NextSubKey@CRegistry@@QEAAKXZ; CRegistry::NextSubKey(void)
0x14001312f  jmp     loc_140013013
0x140013134  lea     rcx, [rsp+318h+var_2A8]; this
0x140013139  call    ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x14001313e  nop
0x14001313f  lea     rcx, [rsp+318h+var_2D8]; this
0x140013144  call    ??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x140013149  nop
0x14001314a  lea     rcx, [rsp+318h+var_2A8]; this
0x14001314f  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x140013154  mov     eax, edi
0x140013156  mov     rcx, [rsp+318h+var_48]
0x14001315e  xor     rcx, rsp; StackCookie
0x140013161  call    __security_check_cookie
0x140013166  add     rsp, 2E0h
0x14001316d  pop     r15
0x14001316f  pop     r14
0x140013171  pop     r13
0x140013173  pop     r12
0x140013175  pop     rdi
0x140013176  pop     rsi
0x140013177  pop     rbx
0x140013178  retn
```
