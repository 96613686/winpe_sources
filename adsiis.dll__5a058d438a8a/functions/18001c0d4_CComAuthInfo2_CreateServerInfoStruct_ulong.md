# CComAuthInfo2::CreateServerInfoStruct(ulong)

- ea: `0x18001c0d4`
- end: `0x18001c2d6`
- name: `?CreateServerInfoStruct@CComAuthInfo2@@QEBAPEAU_COSERVERINFO@@K@Z`
- size: `514`
- prototype: `struct _COSERVERINFO *__fastcall(CComAuthInfo2 *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013430`
- `0x18001a578`
- `0x18001bf94`

## callees

- `0x1800010b0`
- `0x1800010f0`
- `0x180012ccc`
- `0x18001c0d4`
- `0x18001c4b8`
- `0x18001c558`
- `0x18001c580`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001c2aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c2b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c2bc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c2aa`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c2b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c2bc`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c1ca`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c1e4`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c208`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c222`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c242`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c25c`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c1ca`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c1e4`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c208`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c222`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c242`
- `OLEAUT32!__imp_SysStringLen` at `0x18001c25c`

## pseudocode

```c
struct _COSERVERINFO *__fastcall CComAuthInfo2::CreateServerInfoStruct(CComAuthInfo2 *this)
{
  _OWORD *v3; // rax
  _OWORD *v4; // rbp
  _OWORD *v5; // r14
  _OWORD *v6; // rax
  _OWORD *v7; // r15
  unsigned __int16 *v8; // rax
  OLECHAR *v9; // rdi
  OLECHAR *v10; // rsi
  UINT v11; // eax
  UINT v12; // eax
  OLECHAR *v13; // rbx
  UINT v14; // eax
  UINT v15; // eax
  UINT v16; // eax
  UINT v17; // eax
  BSTR pbstr; // [rsp+50h] [rbp+8h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+18h] BYREF

  if ( *((_DWORD *)this + 6) && !(unsigned int)CComAuthInfo2::UsesImpersonation(this) )
    return 0;
  v3 = operator new(0x20u);
  v4 = v3;
  if ( v3 )
  {
    *v3 = 0;
    v3[1] = 0;
    *((_QWORD *)v3 + 1) = *(_QWORD *)this;
    if ( (unsigned int)CComAuthInfo2::UsesImpersonation(this) )
    {
      v5 = operator new(0x28u);
      if ( v5 )
      {
        *v5 = 0;
        v5[1] = 0;
        *((_QWORD *)v5 + 4) = 0;
        v6 = operator new(0x30u);
        v7 = v6;
        if ( v6 )
        {
          *v6 = 0;
          v6[1] = 0;
          v6[2] = 0;
          pbstr = ATL::CComBSTR::Copy((CComAuthInfo2 *)((char *)this + 8));
          v8 = ATL::CComBSTR::Copy((CComAuthInfo2 *)((char *)this + 16));
          bstrString = 0;
          v9 = v8;
          CComAuthInfo2::SplitUserNameAndDomain((struct ATL::CComBSTR *)&pbstr, (struct ATL::CComBSTR *)&bstrString);
          v10 = pbstr;
          if ( pbstr )
            v11 = SysStringLen(pbstr);
          else
            v11 = 0;
          *((_DWORD *)v7 + 2) = v11;
          if ( v11 )
          {
            if ( v10 )
              v12 = SysStringLen(v10);
            else
              v12 = 0;
            *(_QWORD *)v7 = XAllocString(v10, v12);
          }
          v13 = bstrString;
          if ( bstrString )
            v14 = SysStringLen(bstrString);
          else
            v14 = 0;
          *((_DWORD *)v7 + 6) = v14;
          if ( v14 )
          {
            if ( v13 )
              v15 = SysStringLen(v13);
            else
              v15 = 0;
            *((_QWORD *)v7 + 2) = XAllocString(v13, v15);
          }
          if ( v9 )
            v16 = SysStringLen(v9);
          else
            v16 = 0;
          *((_DWORD *)v7 + 10) = v16;
          if ( v16 )
          {
            if ( v9 )
              v17 = SysStringLen(v9);
            else
              v17 = 0;
            *((_QWORD *)v7 + 4) = XAllocString(v9, v17);
          }
          *((_DWORD *)v5 + 4) = 0;
          *((_DWORD *)v7 + 11) = 2;
          *((_DWORD *)v5 + 5) = 3;
          *(_QWORD *)v5 = 9;
          *((_QWORD *)v5 + 1) = 0;
          *((_DWORD *)v5 + 8) = 0;
          *((_QWORD *)v5 + 3) = v7;
          *((_QWORD *)v4 + 2) = v5;
          SysFreeString(v13);
          SysFreeString(v9);
          SysFreeString(v10);
        }
        else
        {
          operator delete(v5);
        }
      }
    }
  }
  return (struct _COSERVERINFO *)v4;
}

```

## disassembly

```asm
0x18001c0d4  mov     [rsp+arg_8], rbx
0x18001c0d9  push    rbp
0x18001c0da  push    rsi
0x18001c0db  push    rdi
0x18001c0dc  push    r14
0x18001c0de  push    r15
0x18001c0e0  sub     rsp, 20h
0x18001c0e4  cmp     dword ptr [rcx+18h], 0
0x18001c0e8  mov     rbx, rcx
0x18001c0eb  jz      short loc_18001C0FD
0x18001c0ed  call    ?UsesImpersonation@CComAuthInfo2@@QEBAHXZ; CComAuthInfo2::UsesImpersonation(void)
0x18001c0f2  test    eax, eax
0x18001c0f4  jnz     short loc_18001C0FD
0x18001c0f6  xor     eax, eax
0x18001c0f8  jmp     loc_18001C2C5
0x18001c0fd  mov     ecx, 20h ; ' '; Size
0x18001c102  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c107  mov     rbp, rax
0x18001c10a  test    rax, rax
0x18001c10d  jz      loc_18001C2C2
0x18001c113  xorps   xmm0, xmm0
0x18001c116  movups  xmmword ptr [rax], xmm0
0x18001c119  movups  xmmword ptr [rax+10h], xmm0
0x18001c11d  mov     rcx, [rbx]
0x18001c120  mov     [rax+8], rcx
0x18001c124  mov     rcx, rbx; this
0x18001c127  call    ?UsesImpersonation@CComAuthInfo2@@QEBAHXZ; CComAuthInfo2::UsesImpersonation(void)
0x18001c12c  test    eax, eax
0x18001c12e  jz      loc_18001C2C2
0x18001c134  mov     ecx, 28h ; '('; Size
0x18001c139  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c13e  mov     r14, rax
0x18001c141  test    rax, rax
0x18001c144  jz      loc_18001C2C2
0x18001c14a  xor     eax, eax
0x18001c14c  xorps   xmm0, xmm0
0x18001c14f  movups  xmmword ptr [r14], xmm0
0x18001c153  movups  xmmword ptr [r14+10h], xmm0
0x18001c158  lea     ecx, [rax+30h]; Size
0x18001c15b  mov     [r14+20h], rax
0x18001c15f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c164  mov     r15, rax
0x18001c167  test    rax, rax
0x18001c16a  jnz     short loc_18001C179
0x18001c16c  mov     rcx, r14; Block
0x18001c16f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001c174  jmp     loc_18001C2C2
0x18001c179  xorps   xmm0, xmm0
0x18001c17c  lea     rcx, [rbx+8]; this
0x18001c180  movups  xmmword ptr [rax], xmm0
0x18001c183  movups  xmmword ptr [rax+10h], xmm0
0x18001c187  movups  xmmword ptr [rax+20h], xmm0
0x18001c18b  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18001c190  lea     rcx, [rbx+10h]; this
0x18001c194  mov     [rsp+48h+pbstr], rax
0x18001c199  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18001c19e  lea     rdx, [rsp+48h+bstrString]; struct ATL::CComBSTR *
0x18001c1a3  mov     [rsp+48h+bstrString], 0
0x18001c1ac  lea     rcx, [rsp+48h+pbstr]; struct ATL::CComBSTR *
0x18001c1b1  mov     rdi, rax
0x18001c1b4  call    ?SplitUserNameAndDomain@CComAuthInfo2@@SAHAEAVCComBSTR@ATL@@0@Z; CComAuthInfo2::SplitUserNameAndDomain(ATL::CComBSTR &,ATL::CComBSTR &)
0x18001c1b9  mov     rsi, [rsp+48h+pbstr]
0x18001c1be  test    rsi, rsi
0x18001c1c1  jnz     short loc_18001C1C7
0x18001c1c3  xor     eax, eax
0x18001c1c5  jmp     short loc_18001C1D0
0x18001c1c7  mov     rcx, rsi; pbstr
0x18001c1ca  call    cs:__imp_SysStringLen
0x18001c1d0  mov     [r15+8], eax
0x18001c1d4  test    eax, eax
0x18001c1d6  jz      short loc_18001C1F7
0x18001c1d8  test    rsi, rsi
0x18001c1db  jnz     short loc_18001C1E1
0x18001c1dd  xor     eax, eax
0x18001c1df  jmp     short loc_18001C1EA
0x18001c1e1  mov     rcx, rsi; pbstr
0x18001c1e4  call    cs:__imp_SysStringLen
0x18001c1ea  mov     edx, eax; int
0x18001c1ec  mov     rcx, rsi; unsigned __int16 *
0x18001c1ef  call    ?XAllocString@@YAPEAGPEBGH@Z; XAllocString(ushort const *,int)
0x18001c1f4  mov     [r15], rax
0x18001c1f7  mov     rbx, [rsp+48h+bstrString]
0x18001c1fc  test    rbx, rbx
0x18001c1ff  jnz     short loc_18001C205
0x18001c201  xor     eax, eax
0x18001c203  jmp     short loc_18001C20E
0x18001c205  mov     rcx, rbx; pbstr
0x18001c208  call    cs:__imp_SysStringLen
0x18001c20e  mov     [r15+18h], eax
0x18001c212  test    eax, eax
0x18001c214  jz      short loc_18001C236
0x18001c216  test    rbx, rbx
0x18001c219  jnz     short loc_18001C21F
0x18001c21b  xor     eax, eax
0x18001c21d  jmp     short loc_18001C228
0x18001c21f  mov     rcx, rbx; pbstr
0x18001c222  call    cs:__imp_SysStringLen
0x18001c228  mov     edx, eax; int
0x18001c22a  mov     rcx, rbx; unsigned __int16 *
0x18001c22d  call    ?XAllocString@@YAPEAGPEBGH@Z; XAllocString(ushort const *,int)
0x18001c232  mov     [r15+10h], rax
0x18001c236  test    rdi, rdi
0x18001c239  jnz     short loc_18001C23F
0x18001c23b  xor     eax, eax
0x18001c23d  jmp     short loc_18001C248
0x18001c23f  mov     rcx, rdi; pbstr
0x18001c242  call    cs:__imp_SysStringLen
0x18001c248  mov     [r15+28h], eax
0x18001c24c  test    eax, eax
0x18001c24e  jz      short loc_18001C270
0x18001c250  test    rdi, rdi
0x18001c253  jnz     short loc_18001C259
0x18001c255  xor     eax, eax
0x18001c257  jmp     short loc_18001C262
0x18001c259  mov     rcx, rdi; pbstr
0x18001c25c  call    cs:__imp_SysStringLen
0x18001c262  mov     edx, eax; int
0x18001c264  mov     rcx, rdi; unsigned __int16 *
0x18001c267  call    ?XAllocString@@YAPEAGPEBGH@Z; XAllocString(ushort const *,int)
0x18001c26c  mov     [r15+20h], rax
0x18001c270  mov     dword ptr [r14+10h], 0
0x18001c278  mov     rcx, rbx; bstrString
0x18001c27b  mov     dword ptr [r15+2Ch], 2
0x18001c283  mov     dword ptr [r14+14h], 3
0x18001c28b  mov     qword ptr [r14], 9
0x18001c292  mov     qword ptr [r14+8], 0
0x18001c29a  mov     dword ptr [r14+20h], 0
0x18001c2a2  mov     [r14+18h], r15
0x18001c2a6  mov     [rbp+10h], r14
0x18001c2aa  call    cs:__imp_SysFreeString
0x18001c2b0  mov     rcx, rdi; bstrString
0x18001c2b3  call    cs:__imp_SysFreeString
0x18001c2b9  mov     rcx, rsi; bstrString
0x18001c2bc  call    cs:__imp_SysFreeString
0x18001c2c2  mov     rax, rbp
0x18001c2c5  mov     rbx, [rsp+48h+arg_8]
0x18001c2ca  add     rsp, 20h
0x18001c2ce  pop     r15
0x18001c2d0  pop     r14
0x18001c2d2  pop     rdi
0x18001c2d3  pop     rsi
0x18001c2d4  pop     rbp
0x18001c2d5  retn
```
