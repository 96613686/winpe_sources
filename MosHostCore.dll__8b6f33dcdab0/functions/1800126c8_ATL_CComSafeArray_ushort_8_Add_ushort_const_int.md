# ATL::CComSafeArray<ushort *,8>::Add(ushort * const &,int)

- ea: `0x1800126c8`
- end: `0x180012821`
- name: `?Add@?$CComSafeArray@PEAG$07@ATL@@QEAAJAEBQEAGH@Z`
- size: `345`
- prototype: `HRESULT __fastcall(SAFEARRAY **, _QWORD *, LONG)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001be24`

## callees

- `0x18000ec4c`
- `0x1800126c8`
- `0x180016364`
- `0x18001644c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800127f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800127f6`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800126fb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800126fb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800127c9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800127c9`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180012716`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001278a`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180012716`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001278a`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180012763`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180012763`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180012779`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180012779`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall ATL::CComSafeArray<unsigned short *,8>::Add(SAFEARRAY **a1, _QWORD *a2, LONG a3)
{
  SAFEARRAY *v5; // rax
  HRESULT result; // eax
  LONG LowerBound; // edi
  int Count; // eax
  SAFEARRAY *v9; // rcx
  int v10; // eax
  LONG v11; // edi
  LONG v12; // esi
  SAFEARRAY *v13; // rcx
  HRESULT UBound; // eax
  __int64 v15; // rdi
  OLECHAR *v16; // rcx
  SAFEARRAYBOUND psaboundNew; // [rsp+40h] [rbp+8h] BYREF
  LONG plUbound; // [rsp+50h] [rbp+18h] BYREF

  plUbound = a3;
  if ( *a1 )
    goto LABEL_5;
  psaboundNew = 0;
  v5 = SafeArrayCreate(8u, 1u, &psaboundNew);
  *a1 = v5;
  if ( !v5 )
    return -2147024882;
  result = SafeArrayLock(v5);
  if ( result >= 0 )
  {
LABEL_5:
    LowerBound = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(a1);
    Count = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
    v9 = *a1;
    psaboundNew.cElements = Count + 1;
    psaboundNew.lLbound = LowerBound;
    if ( !v9 )
      ATL::AtlThrowImpl(-2147467259);
    if ( (v9->fFeatures & 0x10) != 0 )
    {
      return -2147467259;
    }
    else
    {
      result = SafeArrayUnlock(v9);
      if ( result >= 0 )
      {
        result = SafeArrayRedim(*a1, &psaboundNew);
        if ( result >= 0 )
        {
          result = SafeArrayLock(*a1);
          if ( result >= 0 )
          {
            v10 = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
            if ( !*a2 )
              return -2147024809;
            v11 = v10 - 1 + LowerBound;
            v12 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(a1);
            if ( v11 < v12 )
              return -2147024809;
            v13 = *a1;
            plUbound = 0;
            UBound = SafeArrayGetUBound(v13, 1u, &plUbound);
            if ( UBound < 0 )
              ATL::AtlThrowImpl(UBound);
            if ( v11 <= plUbound )
            {
              v15 = v11 - v12;
              v16 = (OLECHAR *)*((_QWORD *)(*a1)->pvData + v15);
              if ( v16 )
                SysFreeString(v16);
              *((_QWORD *)(*a1)->pvData + v15) = *a2;
              return 0;
            }
            else
            {
              return -2147024809;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800126c8  mov     rax, rsp
0x1800126cb  mov     [rax+10h], rbx
0x1800126cf  mov     [rax+18h], r8d
0x1800126d3  push    rsi
0x1800126d4  push    rdi
0x1800126d5  push    r14
0x1800126d7  sub     rsp, 20h
0x1800126db  cmp     qword ptr [rcx], 0
0x1800126df  mov     r14, rdx
0x1800126e2  mov     rbx, rcx
0x1800126e5  jnz     short loc_180012724
0x1800126e7  mov     ecx, 8; vt
0x1800126ec  mov     qword ptr [rax+8], 0
0x1800126f4  lea     r8, [rax+8]; rgsabound
0x1800126f8  lea     edx, [rcx-7]; cDims
0x1800126fb  call    cs:__imp_SafeArrayCreate
0x180012701  mov     [rbx], rax
0x180012704  test    rax, rax
0x180012707  jnz     short loc_180012713
0x180012709  mov     eax, 8007000Eh
0x18001270e  jmp     loc_180012813
0x180012713  mov     rcx, rax; psa
0x180012716  call    cs:__imp_SafeArrayLock
0x18001271c  test    eax, eax
0x18001271e  js      loc_180012813
0x180012724  mov     rcx, rbx
0x180012727  call    ?GetLowerBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetLowerBound(uint)
0x18001272c  mov     rcx, rbx
0x18001272f  mov     edi, eax
0x180012731  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x180012736  mov     rcx, [rbx]; psa
0x180012739  inc     eax
0x18001273b  mov     [rsp+38h+psaboundNew.cElements], eax
0x18001273f  mov     [rsp+38h+psaboundNew.lLbound], edi
0x180012743  test    rcx, rcx
0x180012746  jnz     short loc_180012753
0x180012748  mov     ecx, 80004005h; int
0x18001274d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180012753  test    byte ptr [rcx+2], 10h
0x180012757  jz      short loc_180012763
0x180012759  mov     eax, 80004005h
0x18001275e  jmp     loc_180012813
0x180012763  call    cs:__imp_SafeArrayUnlock
0x180012769  test    eax, eax
0x18001276b  js      loc_180012813
0x180012771  mov     rcx, [rbx]; psa
0x180012774  lea     rdx, [rsp+38h+psaboundNew]; psaboundNew
0x180012779  call    cs:__imp_SafeArrayRedim
0x18001277f  test    eax, eax
0x180012781  js      loc_180012813
0x180012787  mov     rcx, [rbx]; psa
0x18001278a  call    cs:__imp_SafeArrayLock
0x180012790  test    eax, eax
0x180012792  js      short loc_180012813
0x180012794  mov     rcx, rbx
0x180012797  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18001279c  cmp     qword ptr [r14], 0
0x1800127a0  jz      short loc_18001280E
0x1800127a2  dec     eax
0x1800127a4  mov     rcx, rbx
0x1800127a7  add     edi, eax
0x1800127a9  call    ?GetLowerBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetLowerBound(uint)
0x1800127ae  mov     esi, eax
0x1800127b0  cmp     edi, eax
0x1800127b2  jl      short loc_18001280E
0x1800127b4  mov     rcx, [rbx]; psa
0x1800127b7  lea     r8, [rsp+38h+plUbound]; plUbound
0x1800127bc  mov     edx, 1; nDim
0x1800127c1  mov     [rsp+38h+plUbound], 0
0x1800127c9  call    cs:__imp_SafeArrayGetUBound
0x1800127cf  test    eax, eax
0x1800127d1  jns     short loc_1800127DB
0x1800127d3  mov     ecx, eax; int
0x1800127d5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800127db  cmp     edi, [rsp+38h+plUbound]
0x1800127df  jg      short loc_18001280E
0x1800127e1  mov     rax, [rbx]
0x1800127e4  sub     edi, esi
0x1800127e6  movsxd  rdi, edi
0x1800127e9  mov     rcx, [rax+10h]
0x1800127ed  mov     rcx, [rcx+rdi*8]; bstrString
0x1800127f1  test    rcx, rcx
0x1800127f4  jz      short loc_1800127FC
0x1800127f6  call    cs:__imp_SysFreeString
0x1800127fc  mov     rax, [rbx]
0x1800127ff  mov     rcx, [rax+10h]
0x180012803  mov     rax, [r14]
0x180012806  mov     [rcx+rdi*8], rax
0x18001280a  xor     eax, eax
0x18001280c  jmp     short loc_180012813
0x18001280e  mov     eax, 80070057h
0x180012813  mov     rbx, [rsp+38h+arg_8]
0x180012818  add     rsp, 20h
0x18001281c  pop     r14
0x18001281e  pop     rdi
0x18001281f  pop     rsi
0x180012820  retn
```
