# _IsValidWindow

- ea: `0x14000c0c0`
- end: `0x14000c2d6`
- name: `_IsValidWindow`
- size: `534`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140009e50`
- `0x14000a330`
- `0x14000a4b0`

## callees

- `0x140002c70`
- `0x140003a8c`
- `0x14000429c`
- `0x14000c01c`
- `0x14000c0c0`
- `0x14000cca0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x14000c266`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x14000c266`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c11e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c2b1`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c11e`
- `OLEAUT32!__imp_SysFreeString` at `0x14000c2b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall IsValidWindow(__int64 a1)
{
  OLECHAR *v2; // rcx
  char v4; // di
  int v5; // eax
  const wchar_t *v6; // r9
  PARSEDURLW ppu; // [rsp+30h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp+10h] BYREF
  __int64 v9; // [rsp+78h] [rbp+18h] BYREF

  v9 = 0;
  v2 = 0;
  bstrString = 0;
  if ( a1 )
  {
    if ( (unsigned __int8)IsTopWindow(a1) )
    {
      v4 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 416LL))(a1, &v9);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v9 + 320LL))(v9, &bstrString);
        if ( v5 >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              0xEu,
              &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
              bstrString);
          }
          memset(&ppu, 0, sizeof(ppu));
          ppu.cbSize = 40;
          if ( ParseURLW(bstrString, &ppu) < 0 || ppu.nScheme - 15 > 2 )
          {
            v4 = 1;
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0xFu, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
          }
          goto LABEL_32;
        }
        v6 = L"get_URL";
      }
      else
      {
        v6 = L"get_document";
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          16,
          (unsigned int)&WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
          (_DWORD)v6,
          v5);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0xDu, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
      }
      v4 = 0;
    }
LABEL_32:
    SysFreeString(bstrString);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    return v4;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 0xCu, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
    v2 = bstrString;
  }
  SysFreeString(v2);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  return 0;
}

```

## disassembly

```asm
0x14000c0c0  mov     [rsp-8+arg_10], rbx
0x14000c0c5  mov     [rsp-8+arg_18], rdi
0x14000c0ca  push    rbp
0x14000c0cb  mov     rbp, rsp
0x14000c0ce  sub     rsp, 60h
0x14000c0d2  mov     rbx, rcx
0x14000c0d5  mov     [rbp+arg_8], 0
0x14000c0dd  xor     ecx, ecx
0x14000c0df  mov     [rbp+bstrString], rcx
0x14000c0e3  test    rbx, rbx
0x14000c0e6  jnz     short loc_14000C135
0x14000c0e8  lea     rbx, WPP_GLOBAL_Control
0x14000c0ef  mov     rax, cs:WPP_GLOBAL_Control
0x14000c0f6  cmp     rax, rbx
0x14000c0f9  jz      short loc_14000C11E
0x14000c0fb  test    byte ptr [rax+44h], 4
0x14000c0ff  jz      short loc_14000C11E
0x14000c101  cmp     byte ptr [rax+41h], 5
0x14000c105  jb      short loc_14000C11E
0x14000c107  lea     edx, [rcx+0Ch]
0x14000c10a  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000c111  mov     rcx, [rax+38h]
0x14000c115  call    WPP_SF_
0x14000c11a  mov     rcx, [rbp+bstrString]; bstrString
0x14000c11e  call    cs:__imp_SysFreeString
0x14000c124  nop
0x14000c125  lea     rcx, [rbp+arg_8]
0x14000c129  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000c12e  xor     al, al
0x14000c130  jmp     loc_14000C2C4
0x14000c135  mov     rcx, rbx
0x14000c138  call    _IsTopWindow
0x14000c13d  test    al, al
0x14000c13f  jnz     short loc_14000C17D
0x14000c141  lea     rbx, WPP_GLOBAL_Control
0x14000c148  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c14f  cmp     rcx, rbx
0x14000c152  jz      short loc_14000C175
0x14000c154  test    byte ptr [rcx+44h], 4
0x14000c158  jz      short loc_14000C175
0x14000c15a  cmp     byte ptr [rcx+41h], 5
0x14000c15e  jb      short loc_14000C175
0x14000c160  mov     edx, 0Dh
0x14000c165  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000c16c  mov     rcx, [rcx+38h]
0x14000c170  call    WPP_SF_
0x14000c175  xor     dil, dil
0x14000c178  jmp     loc_14000C2AD
0x14000c17d  xor     dil, dil
0x14000c180  mov     rax, [rbx]
0x14000c183  lea     rdx, [rbp+arg_8]
0x14000c187  mov     rcx, rbx
0x14000c18a  mov     rax, [rax+1A0h]
0x14000c191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c196  test    eax, eax
0x14000c198  jns     short loc_14000C1A3
0x14000c19a  lea     r9, aGetDocument; "get_document"
0x14000c1a1  jmp     short loc_14000C1C5
0x14000c1a3  mov     rcx, [rbp+arg_8]
0x14000c1a7  mov     rax, [rcx]
0x14000c1aa  lea     rdx, [rbp+bstrString]
0x14000c1ae  mov     rax, [rax+140h]
0x14000c1b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c1ba  test    eax, eax
0x14000c1bc  jns     short loc_14000C20E
0x14000c1be  lea     r9, aGetUrl; "get_URL"
0x14000c1c5  lea     rbx, WPP_GLOBAL_Control
0x14000c1cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c1d3  cmp     rcx, rbx
0x14000c1d6  jz      loc_14000C2AD
0x14000c1dc  test    byte ptr [rcx+44h], 4
0x14000c1e0  jz      loc_14000C2AD
0x14000c1e6  cmp     byte ptr [rcx+41h], 2
0x14000c1ea  jb      loc_14000C2AD
0x14000c1f0  mov     edx, 10h
0x14000c1f5  mov     [rsp+60h+var_40], eax
0x14000c1f9  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000c200  mov     rcx, [rcx+38h]
0x14000c204  call    WPP_SF_Sd
0x14000c209  jmp     loc_14000C2AD
0x14000c20e  lea     rbx, WPP_GLOBAL_Control
0x14000c215  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c21c  cmp     rcx, rbx
0x14000c21f  jz      short loc_14000C246
0x14000c221  test    byte ptr [rcx+44h], 4
0x14000c225  jz      short loc_14000C246
0x14000c227  cmp     byte ptr [rcx+41h], 5
0x14000c22b  jb      short loc_14000C246
0x14000c22d  mov     edx, 0Eh
0x14000c232  mov     r9, [rbp+bstrString]
0x14000c236  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000c23d  mov     rcx, [rcx+38h]
0x14000c241  call    WPP_SF_S
0x14000c246  xorps   xmm0, xmm0
0x14000c249  xor     eax, eax
0x14000c24b  movups  xmmword ptr [rbp+ppu.cbSize], xmm0
0x14000c24f  movups  xmmword ptr [rbp+ppu.cchProtocol], xmm0
0x14000c253  mov     qword ptr [rbp+ppu.cchSuffix], rax
0x14000c257  mov     [rbp+ppu.cbSize], 28h ; '('
0x14000c25e  lea     rdx, [rbp+ppu]; ppu
0x14000c262  mov     rcx, [rbp+bstrString]; pcszURL
0x14000c266  call    cs:__imp_ParseURLW
0x14000c26c  test    eax, eax
0x14000c26e  js      short loc_14000C2AA
0x14000c270  mov     eax, [rbp+ppu.nScheme]
0x14000c273  add     eax, 0FFFFFFF1h
0x14000c276  cmp     eax, 2
0x14000c279  ja      short loc_14000C2AA
0x14000c27b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c282  cmp     rcx, rbx
0x14000c285  jz      short loc_14000C2AD
0x14000c287  test    byte ptr [rcx+44h], 4
0x14000c28b  jz      short loc_14000C2AD
0x14000c28d  cmp     byte ptr [rcx+41h], 5
0x14000c291  jb      short loc_14000C2AD
0x14000c293  mov     edx, 0Fh
0x14000c298  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000c29f  mov     rcx, [rcx+38h]
0x14000c2a3  call    WPP_SF_
0x14000c2a8  jmp     short loc_14000C2AD
0x14000c2aa  mov     dil, 1
0x14000c2ad  mov     rcx, [rbp+bstrString]; bstrString
0x14000c2b1  call    cs:__imp_SysFreeString
0x14000c2b7  nop
0x14000c2b8  lea     rcx, [rbp+arg_8]
0x14000c2bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000c2c1  mov     al, dil
0x14000c2c4  lea     r11, [rsp+60h+var_s0]
0x14000c2c9  mov     rbx, [r11+20h]
0x14000c2cd  mov     rdi, [r11+28h]
0x14000c2d1  mov     rsp, r11
0x14000c2d4  pop     rbp
0x14000c2d5  retn
```
