# ComActivityAssetDataToCDPActivityAsset

- ea: `0x1800148d8`
- end: `0x1800149f0`
- name: `ComActivityAssetDataToCDPActivityAsset`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800145f0`

## callees

- `0x1800097d0`
- `0x1800147f8`
- `0x1800148d8`
- `0x18001e798`
- `0x180064010`

## import_xrefs

- `cdp!CDPCreateTestActivityAsset` at `0x18001495d`
- `cdp!CDPCreateTestActivityAsset` at `0x18001495d`
- `cdp!CDPCreateActivityAsset` at `0x18001499d`
- `cdp!CDPCreateActivityAsset` at `0x18001499d`

## string_xrefs

- `0x1800148fc`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x180014977`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ComActivityAssetDataToCDPActivityAsset(__int64 *a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rax
  bool v9; // zf
  int v10; // edi
  __int64 v11; // rdx
  std::_Ref_count_base *v12[2]; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v13[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]

  if ( !a1 )
  {
    v3 = -2147024809;
    v4 = 1073;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)v3,
      (int)v12[0]);
    return v3;
  }
  if ( !a2 )
  {
    v3 = -2147467261;
    v4 = 1074;
    goto LABEL_3;
  }
  *a2 = 0;
  *(_OWORD *)v12 = 0;
  v6 = a1[1];
  v7 = *((unsigned int *)a1 + 4);
  v8 = *a1;
  v13[0] = 0;
  v9 = *((_DWORD *)a1 + 5) == 1;
  v13[1] = v12;
  if ( v9 )
  {
    v10 = CDPCreateTestActivityAsset(v8, v7, v6, v13);
    cdp::detail::address_of<ICDPActivityAsset>::~address_of<ICDPActivityAsset>(v13);
    if ( v10 < 0 )
    {
      v11 = 1082;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)(unsigned int)v10,
        (int)v12[0]);
      if ( v12[1] )
        std::_Ref_count_base::_Decref(v12[1]);
      return (unsigned int)v10;
    }
  }
  else
  {
    v10 = CDPCreateActivityAsset(v8, v7, v6, v13);
    cdp::detail::address_of<ICDPActivityAsset>::~address_of<ICDPActivityAsset>(v13);
    if ( v10 < 0 )
    {
      v11 = 1087;
      goto LABEL_9;
    }
  }
  (*(void (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v12[0] + 8LL))(v12[0]);
  *a2 = v12[0];
  if ( v12[1] )
    std::_Ref_count_base::_Decref(v12[1]);
  return 0;
}

```

## disassembly

```asm
0x1800148d8  mov     [rsp-8+arg_0], rbx
0x1800148dd  mov     [rsp-8+arg_8], rdi
0x1800148e2  push    rbp
0x1800148e3  mov     rbp, rsp
0x1800148e6  sub     rsp, 40h
0x1800148ea  mov     rbx, rdx
0x1800148ed  test    rcx, rcx
0x1800148f0  jnz     short loc_180014916
0x1800148f2  mov     ebx, 80070057h
0x1800148f7  mov     edx, 431h; void *
0x1800148fc  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x180014903  mov     r9d, ebx; char *
0x180014906  mov     rcx, [rbp+8]; this
0x18001490a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001490f  mov     eax, ebx
0x180014911  jmp     loc_1800149E0
0x180014916  test    rbx, rbx
0x180014919  jnz     short loc_180014927
0x18001491b  mov     ebx, 80004003h
0x180014920  mov     edx, 432h
0x180014925  jmp     short loc_1800148FC
0x180014927  mov     qword ptr [rdx], 0
0x18001492e  xorps   xmm0, xmm0
0x180014931  movdqu  xmmword ptr [rbp+var_20], xmm0
0x180014936  mov     r8, [rcx+8]
0x18001493a  mov     edx, [rcx+10h]
0x18001493d  mov     rax, [rcx]
0x180014940  mov     [rbp+var_10], 0
0x180014948  lea     r9, [rbp+var_10]
0x18001494c  cmp     dword ptr [rcx+14h], 1
0x180014950  lea     rcx, [rbp+var_20]
0x180014954  mov     [rbp+var_8], rcx
0x180014958  mov     rcx, rax
0x18001495b  jnz     short loc_18001499D
0x18001495d  call    cs:__imp_CDPCreateTestActivityAsset
0x180014963  mov     edi, eax
0x180014965  lea     rcx, [rbp+var_10]
0x180014969  call    ??1?$address_of@VICDPActivityAsset@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPActivityAsset>::~address_of<ICDPActivityAsset>(void)
0x18001496e  test    edi, edi
0x180014970  jns     short loc_1800149B9
0x180014972  mov     edx, 43Ah; void *
0x180014977  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18001497e  mov     r9d, edi; char *
0x180014981  mov     rcx, [rbp+8]; this
0x180014985  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001498a  nop
0x18001498b  mov     rcx, [rbp+var_20+8]; this
0x18001498f  test    rcx, rcx
0x180014992  jz      short loc_180014999
0x180014994  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014999  mov     eax, edi
0x18001499b  jmp     short loc_1800149E0
0x18001499d  call    cs:__imp_CDPCreateActivityAsset
0x1800149a3  mov     edi, eax
0x1800149a5  lea     rcx, [rbp+var_10]
0x1800149a9  call    ??1?$address_of@VICDPActivityAsset@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPActivityAsset>::~address_of<ICDPActivityAsset>(void)
0x1800149ae  test    edi, edi
0x1800149b0  jns     short loc_1800149B9
0x1800149b2  mov     edx, 43Fh
0x1800149b7  jmp     short loc_180014977
0x1800149b9  mov     rcx, [rbp+var_20]
0x1800149bd  mov     rax, [rcx]
0x1800149c0  mov     rax, [rax+8]
0x1800149c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149c9  mov     rax, [rbp+var_20]
0x1800149cd  mov     [rbx], rax
0x1800149d0  mov     rcx, [rbp+var_20+8]; this
0x1800149d4  test    rcx, rcx
0x1800149d7  jz      short loc_1800149DE
0x1800149d9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800149de  xor     eax, eax
0x1800149e0  mov     rbx, [rsp+40h+arg_0]
0x1800149e5  mov     rdi, [rsp+40h+arg_8]
0x1800149ea  add     rsp, 40h
0x1800149ee  pop     rbp
0x1800149ef  retn
```
