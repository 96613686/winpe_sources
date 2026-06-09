# ATL::CComSafeArray<ushort *,8>::Add(ushort * const &,int)

- ea: `0x18000dbe8`
- end: `0x18000dd0d`
- name: `?Add@?$CComSafeArray@PEAG$07@ATL@@QEAAJAEBQEAGH@Z`
- size: `293`
- prototype: `HRESULT __fastcall(SAFEARRAY **, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f240`

## callees

- `0x18000dbe8`
- `0x18000ddb4`
- `0x18000ed74`
- `0x18000f6cc`
- `0x18000f87c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000dce6`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dce6`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000dc14`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000dc14`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18000dc2f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18000dc9b`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18000dc2f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18000dc9b`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000dc7c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000dc7c`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000dc8e`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000dc8e`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<unsigned short *,8>::Add(SAFEARRAY **a1, _QWORD *a2)
{
  SAFEARRAY *v4; // rax
  HRESULT result; // eax
  LONG LowerBound; // edi
  int Count; // eax
  SAFEARRAY *v8; // rcx
  int v9; // eax
  int v10; // edi
  int v11; // esi
  __int64 v12; // rdi
  OLECHAR *v13; // rcx
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp+8h] BYREF

  if ( *a1 )
    goto LABEL_5;
  rgsabound = 0;
  v4 = SafeArrayCreate(8u, 1u, &rgsabound);
  *a1 = v4;
  if ( !v4 )
    return -2147024882;
  result = SafeArrayLock(v4);
  if ( result >= 0 )
  {
LABEL_5:
    LowerBound = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(a1);
    Count = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
    v8 = *a1;
    rgsabound.cElements = Count + 1;
    rgsabound.lLbound = LowerBound;
    if ( !v8 )
      ATL::AtlThrowImpl(-2147467259);
    if ( (v8->fFeatures & 0x10) != 0 )
    {
      return -2147467259;
    }
    else
    {
      result = SafeArrayUnlock(v8);
      if ( result >= 0 )
      {
        result = SafeArrayRedim(*a1, &rgsabound);
        if ( result >= 0 )
        {
          result = SafeArrayLock(*a1);
          if ( result >= 0 )
          {
            v9 = ATL::CComSafeArray<unsigned short *,8>::GetCount(a1);
            if ( *a2
              && (v10 = v9 - 1 + LowerBound, v11 = ATL::CComSafeArray<unsigned short *,8>::GetLowerBound(a1), v10 >= v11)
              && v10 <= (int)ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(a1) )
            {
              v12 = v10 - v11;
              v13 = (OLECHAR *)*((_QWORD *)(*a1)->pvData + v12);
              if ( v13 )
                SysFreeString(v13);
              *((_QWORD *)(*a1)->pvData + v12) = *a2;
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
0x18000dbe8  push    rbx
0x18000dbea  push    rsi
0x18000dbeb  push    rdi
0x18000dbec  push    r14
0x18000dbee  sub     rsp, 28h
0x18000dbf2  cmp     qword ptr [rcx], 0
0x18000dbf6  mov     r14, rdx
0x18000dbf9  mov     rbx, rcx
0x18000dbfc  jnz     short loc_18000DC3D
0x18000dbfe  mov     ecx, 8; vt
0x18000dc03  mov     qword ptr [rsp+48h+rgsabound.cElements], 0
0x18000dc0c  lea     r8, [rsp+48h+rgsabound]; rgsabound
0x18000dc11  lea     edx, [rcx-7]; cDims
0x18000dc14  call    cs:__imp_SafeArrayCreate
0x18000dc1a  mov     [rbx], rax
0x18000dc1d  test    rax, rax
0x18000dc20  jnz     short loc_18000DC2C
0x18000dc22  mov     eax, 8007000Eh
0x18000dc27  jmp     loc_18000DD03
0x18000dc2c  mov     rcx, rax; psa
0x18000dc2f  call    cs:__imp_SafeArrayLock
0x18000dc35  test    eax, eax
0x18000dc37  js      loc_18000DD03
0x18000dc3d  mov     rcx, rbx
0x18000dc40  call    ?GetLowerBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetLowerBound(uint)
0x18000dc45  mov     rcx, rbx
0x18000dc48  mov     edi, eax
0x18000dc4a  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18000dc4f  mov     rcx, [rbx]; psa
0x18000dc52  inc     eax
0x18000dc54  mov     [rsp+48h+rgsabound.cElements], eax
0x18000dc58  mov     [rsp+48h+rgsabound.lLbound], edi
0x18000dc5c  test    rcx, rcx
0x18000dc5f  jnz     short loc_18000DC6C
0x18000dc61  mov     ecx, 80004005h; int
0x18000dc66  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000dc6c  test    byte ptr [rcx+2], 10h
0x18000dc70  jz      short loc_18000DC7C
0x18000dc72  mov     eax, 80004005h
0x18000dc77  jmp     loc_18000DD03
0x18000dc7c  call    cs:__imp_SafeArrayUnlock
0x18000dc82  test    eax, eax
0x18000dc84  js      short loc_18000DD03
0x18000dc86  mov     rcx, [rbx]; psa
0x18000dc89  lea     rdx, [rsp+48h+rgsabound]; psaboundNew
0x18000dc8e  call    cs:__imp_SafeArrayRedim
0x18000dc94  test    eax, eax
0x18000dc96  js      short loc_18000DD03
0x18000dc98  mov     rcx, [rbx]; psa
0x18000dc9b  call    cs:__imp_SafeArrayLock
0x18000dca1  test    eax, eax
0x18000dca3  js      short loc_18000DD03
0x18000dca5  mov     rcx, rbx
0x18000dca8  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18000dcad  cmp     qword ptr [r14], 0
0x18000dcb1  jz      short loc_18000DCFE
0x18000dcb3  dec     eax
0x18000dcb5  mov     rcx, rbx
0x18000dcb8  add     edi, eax
0x18000dcba  call    ?GetLowerBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetLowerBound(uint)
0x18000dcbf  mov     esi, eax
0x18000dcc1  cmp     edi, eax
0x18000dcc3  jl      short loc_18000DCFE
0x18000dcc5  mov     rcx, rbx
0x18000dcc8  call    ?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z; ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)
0x18000dccd  cmp     edi, eax
0x18000dccf  jg      short loc_18000DCFE
0x18000dcd1  mov     rax, [rbx]
0x18000dcd4  sub     edi, esi
0x18000dcd6  movsxd  rdi, edi
0x18000dcd9  mov     rcx, [rax+10h]
0x18000dcdd  mov     rcx, [rcx+rdi*8]; bstrString
0x18000dce1  test    rcx, rcx
0x18000dce4  jz      short loc_18000DCEC
0x18000dce6  call    cs:__imp_SysFreeString
0x18000dcec  mov     rax, [rbx]
0x18000dcef  mov     rcx, [rax+10h]
0x18000dcf3  mov     rax, [r14]
0x18000dcf6  mov     [rcx+rdi*8], rax
0x18000dcfa  xor     eax, eax
0x18000dcfc  jmp     short loc_18000DD03
0x18000dcfe  mov     eax, 80070057h
0x18000dd03  add     rsp, 28h
0x18000dd07  pop     r14
0x18000dd09  pop     rdi
0x18000dd0a  pop     rsi
0x18000dd0b  pop     rbx
0x18000dd0c  retn
```
