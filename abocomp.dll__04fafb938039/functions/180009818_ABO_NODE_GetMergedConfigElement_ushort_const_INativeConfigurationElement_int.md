# ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)

- ea: `0x180009818`
- end: `0x180009a0b`
- name: `?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z`
- size: `499`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, const unsigned __int16 *, struct INativeConfigurationElement **, int)`
- caller_count: `14`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18001d690`
- `0x18001df90`
- `0x18001e530`
- `0x18001e820`
- `0x18001ecc0`
- `0x18001eee0`
- `0x18001f1f0`
- `0x18001f8c0`
- `0x18001fe30`
- `0x180020440`
- `0x180020890`
- `0x180021570`
- `0x180023cf0`
- `0x180024a10`

## callees

- `0x180001f90`
- `0x18000341a`
- `0x180003460`
- `0x180009488`
- `0x180009818`
- `0x180027294`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800098da`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800098da`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000991d`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x18000991d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000986a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009896`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000986a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009896`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800099dc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800099e6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800099dc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800099e6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009940`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000997d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009940`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000997d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180009904`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180009904`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800098ee`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800098ee`

## string_xrefs

- `0x1800099a4`: `Failed to GetConfigSection() for section '%ws' at path '%ws'\n`

## pseudocode

```c
__int64 __fastcall ABO_NODE::GetMergedConfigElement(
        ABO_NODE *this,
        const unsigned __int16 *a2,
        struct INativeConfigurationElement **a3,
        int a4)
{
  struct INativeSectionException *v8; // rcx
  int LocationPath; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, const unsigned __int16 *, unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  struct INativeSectionException *v13; // rdi
  const unsigned __int16 *v14; // rax
  ABO_MAPPER_LOG *v15; // rcx
  struct INativeSectionException *v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[56]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v19[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v20[256]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v21[256]; // [rsp+2C0h] [rbp+1C0h] BYREF

  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v19, v20, 0x100u);
  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v18, v21, 0x100u);
  v8 = 0;
  v17 = 0;
  if ( a2 && a3 )
  {
    LocationPath = ABO_NODE::GetLocationPath(this, (struct STRU *)v19, a4);
    if ( LocationPath >= 0 )
    {
      LocationPath = STRU::Copy((STRU *)v18, L"MACHINE/WEBROOT/APPHOST");
      if ( LocationPath >= 0 )
      {
        if ( STRU::IsEmpty((STRU *)v19)
          || (LocationPath = STRU::Append((STRU *)v18, L"/"), LocationPath >= 0)
          && (LocationPath = STRU::Append((STRU *)v18, (const struct STRU *)v19), LocationPath >= 0) )
        {
          v10 = *(_QWORD *)(*((_QWORD *)this + 22) + 24LL);
          v11 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **, _QWORD))(*(_QWORD *)v10 + 24LL);
          Str = STRU::QueryStr((STRU *)v18);
          LocationPath = v11(v10, a2, Str, a3, &v17, 0);
          if ( LocationPath < 0 )
          {
            v13 = v17;
            v14 = STRU::QueryStr((STRU *)v18);
            if ( v13 )
              ABO_MAPPER_LOG::WriteConfigSectionException(v15, a2, v14, v13);
            else
              ABO_MAPPER_LOG::WriteLogEntry(
                (HANDLE *)g_pAboLog,
                L"Failed to GetConfigSection() for section '%ws' at path '%ws'\n",
                a2,
                v14);
          }
        }
      }
    }
    v8 = v17;
  }
  else
  {
    LocationPath = -2147024809;
  }
  if ( v8 )
  {
    (*(void (__fastcall **)(struct INativeSectionException *))(*(_QWORD *)v8 + 16LL))(v8);
    v17 = 0;
  }
  STRU::~STRU((STRU *)v18);
  STRU::~STRU((STRU *)v19);
  return (unsigned int)LocationPath;
}

```

## disassembly

```asm
0x180009818  push    rbp
0x18000981a  push    rbx
0x18000981b  push    rsi
0x18000981c  push    rdi
0x18000981d  push    r14
0x18000981f  lea     rbp, [rsp-3D0h]
0x180009827  sub     rsp, 4D0h
0x18000982e  mov     rax, cs:__security_cookie
0x180009835  xor     rax, rsp
0x180009838  mov     [rbp+3F0h+var_30], rax
0x18000983f  mov     r14, r8
0x180009842  mov     rsi, rdx
0x180009845  mov     rdi, rcx
0x180009848  xor     edx, edx; Val
0x18000984a  mov     r8d, 200h; Size
0x180009850  lea     rcx, [rbp+3F0h+var_430]; void *
0x180009854  mov     ebx, r9d
0x180009857  call    memset_0
0x18000985c  mov     r8d, 100h
0x180009862  lea     rdx, [rbp+3F0h+var_430]
0x180009866  lea     rcx, [rbp+3F0h+var_470]
0x18000986a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009870  xor     edx, edx; Val
0x180009872  lea     rcx, [rbp+3F0h+var_230]; void *
0x180009879  mov     r8d, 200h; Size
0x18000987f  call    memset_0
0x180009884  mov     r8d, 100h
0x18000988a  lea     rdx, [rbp+3F0h+var_230]
0x180009891  lea     rcx, [rsp+4F0h+var_4A8]
0x180009896  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000989c  xor     ecx, ecx
0x18000989e  mov     [rsp+4F0h+var_4B0], rcx
0x1800098a3  test    rsi, rsi
0x1800098a6  jz      loc_1800099B8
0x1800098ac  test    r14, r14
0x1800098af  jz      loc_1800099B8
0x1800098b5  mov     r8d, ebx; int
0x1800098b8  lea     rdx, [rbp+3F0h+var_470]; struct STRU *
0x1800098bc  mov     rcx, rdi; this
0x1800098bf  call    ?GetLocationPath@ABO_NODE@@QEAAJPEAVSTRU@@H@Z; ABO_NODE::GetLocationPath(STRU *,int)
0x1800098c4  mov     ebx, eax
0x1800098c6  test    eax, eax
0x1800098c8  js      loc_180009996
0x1800098ce  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800098d5  lea     rcx, [rsp+4F0h+var_4A8]
0x1800098da  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800098e0  mov     ebx, eax
0x1800098e2  test    eax, eax
0x1800098e4  js      loc_180009996
0x1800098ea  lea     rcx, [rbp+3F0h+var_470]
0x1800098ee  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x1800098f4  test    al, al
0x1800098f6  jnz     short loc_180009929
0x1800098f8  lea     rdx, asc_18002E8E8; "/"
0x1800098ff  lea     rcx, [rsp+4F0h+var_4A8]
0x180009904  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000990a  mov     ebx, eax
0x18000990c  test    eax, eax
0x18000990e  js      loc_180009996
0x180009914  lea     rdx, [rbp+3F0h+var_470]
0x180009918  lea     rcx, [rsp+4F0h+var_4A8]
0x18000991d  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180009923  mov     ebx, eax
0x180009925  test    eax, eax
0x180009927  js      short loc_180009996
0x180009929  mov     rax, [rdi+0B0h]
0x180009930  lea     rcx, [rsp+4F0h+var_4A8]
0x180009935  mov     rdi, [rax+18h]
0x180009939  mov     rax, [rdi]
0x18000993c  mov     rbx, [rax+18h]
0x180009940  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180009946  lea     rcx, [rsp+4F0h+var_4B0]
0x18000994b  mov     [rsp+4F0h+var_4C8], 0
0x180009954  mov     [rsp+4F0h+var_4D0], rcx
0x180009959  mov     r8, rax
0x18000995c  mov     rcx, rdi
0x18000995f  mov     r9, r14
0x180009962  mov     rdx, rsi
0x180009965  mov     rax, rbx
0x180009968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000996d  mov     ebx, eax
0x18000996f  test    eax, eax
0x180009971  jns     short loc_180009996
0x180009973  mov     rdi, [rsp+4F0h+var_4B0]
0x180009978  lea     rcx, [rsp+4F0h+var_4A8]
0x18000997d  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180009983  test    rdi, rdi
0x180009986  jz      short loc_18000999D
0x180009988  mov     r9, rdi; struct INativeSectionException *
0x18000998b  mov     r8, rax; unsigned __int16 *
0x18000998e  mov     rdx, rsi; unsigned __int16 *
0x180009991  call    ?WriteConfigSectionException@ABO_MAPPER_LOG@@QEAAJPEBG0PEAVINativeSectionException@@@Z; ABO_MAPPER_LOG::WriteConfigSectionException(ushort const *,ushort const *,INativeSectionException *)
0x180009996  mov     rcx, [rsp+4F0h+var_4B0]
0x18000999b  jmp     short loc_1800099BD
0x18000999d  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x1800099a4  lea     rdx, aFailedToGetcon; "Failed to GetConfigSection() for sectio"...
0x1800099ab  mov     r9, rax
0x1800099ae  mov     r8, rsi
0x1800099b1  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x1800099b6  jmp     short loc_180009996
0x1800099b8  mov     ebx, 80070057h
0x1800099bd  test    rcx, rcx
0x1800099c0  jz      short loc_1800099D7
0x1800099c2  mov     rax, [rcx]
0x1800099c5  mov     rax, [rax+10h]
0x1800099c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ce  mov     [rsp+4F0h+var_4B0], 0
0x1800099d7  lea     rcx, [rsp+4F0h+var_4A8]
0x1800099dc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800099e2  lea     rcx, [rbp+3F0h+var_470]
0x1800099e6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800099ec  mov     eax, ebx
0x1800099ee  mov     rcx, [rbp+3F0h+var_30]
0x1800099f5  xor     rcx, rsp; StackCookie
0x1800099f8  call    __security_check_cookie
0x1800099fd  add     rsp, 4D0h
0x180009a04  pop     r14
0x180009a06  pop     rdi
0x180009a07  pop     rsi
0x180009a08  pop     rbx
0x180009a09  pop     rbp
0x180009a0a  retn
```
