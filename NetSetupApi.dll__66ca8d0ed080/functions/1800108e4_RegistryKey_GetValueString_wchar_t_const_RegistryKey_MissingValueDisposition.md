# RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)

- ea: `0x1800108e4`
- end: `0x180010a96`
- name: `?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z`
- size: `434`
- prototype: `__int64 __fastcall(HKEY *, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180006af8`

## callees

- `0x180006608`
- `0x1800066c8`
- `0x18000895c`
- `0x18000cab4`
- `0x18000ec70`
- `0x180010548`
- `0x1800108e4`
- `0x180010d94`
- `0x180010e80`

## pseudocode

```c
__int64 __fastcall RegistryKey::GetValueString(HKEY *a1, __int64 a2, const WCHAR *a3)
{
  int v3; // edi
  __int64 v6; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v7; // [rsp+48h] [rbp-C0h]
  __int64 v8; // [rsp+58h] [rbp-B0h]
  _BYTE pExceptionObject[216]; // [rsp+60h] [rbp-A8h] BYREF
  int v10; // [rsp+160h] [rbp+58h] BYREF

  v8 = -2;
  v3 = (int)a3;
  v10 = 0;
  RegistryKey::GetValueBlob(a1, (__int64)&v6, a3, &v10);
  if ( v6 == v7 && !v10 || v10 != 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SDP(*((_QWORD *)WPP_GLOBAL_Control + 2), v7 - v6, v10, v3, v10, v7 - v6);
    HResultException::HResultException((HResultException *)pExceptionObject, -2147023267);
    throw (HResultException *)pExceptionObject;
  }
  if ( v6 == v7 )
  {
    *(_QWORD *)(a2 + 24) = 7;
    *(_QWORD *)(a2 + 16) = 0;
    *(_WORD *)a2 = 0;
  }
  else
  {
    if ( (((_BYTE)v7 - (_BYTE)v6) & 1) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024883);
      throw (HResultException *)pExceptionObject;
    }
    if ( *(_BYTE *)(v7 - 1) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024883);
      throw (HResultException *)pExceptionObject;
    }
    std::wstring::wstring(a2, v6);
  }
  std::vector<unsigned char>::_Tidy((__int64)&v6);
  return a2;
}

```

## disassembly

```asm
0x1800108e4  mov     rax, rsp
0x1800108e7  mov     [rax+20h], r9d
0x1800108eb  push    rbp
0x1800108ec  lea     rbp, [rax-38h]
0x1800108f0  sub     rsp, 130h
0x1800108f7  mov     [rsp+130h+var_E0], 0FFFFFFFFFFFFFFFEh
0x180010900  mov     [rax+8], rbx
0x180010904  mov     [rax+10h], rdi
0x180010908  mov     rdi, r8
0x18001090b  mov     rbx, rdx
0x18001090e  mov     [rbp+30h+arg_18], 0
0x180010915  lea     r9, [rbp+30h+arg_18]
0x180010919  lea     rdx, [rsp+130h+var_F8]
0x18001091e  call    ?GetValueBlob@RegistryKey@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@PEB_WPEAKW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBlob(wchar_t const *,ulong *,RegistryKey::MissingValueDisposition)
0x180010923  nop
0x180010924  mov     r8d, [rbp+30h+arg_18]
0x180010928  mov     r10, [rsp+130h+var_F8]
0x18001092d  mov     rdx, [rsp+130h+var_F0]
0x180010932  cmp     r10, rdx
0x180010935  jnz     short loc_18001093C
0x180010937  test    r8d, r8d
0x18001093a  jz      short loc_180010942
0x18001093c  cmp     r8d, 1
0x180010940  jz      short loc_180010995
0x180010942  lea     rax, WPP_GLOBAL_Control
0x180010949  mov     rcx, cs:WPP_GLOBAL_Control
0x180010950  cmp     rcx, rax
0x180010953  jz      short loc_180010974
0x180010955  cmp     byte ptr [rcx+19h], 2
0x180010959  jb      short loc_180010974
0x18001095b  sub     rdx, r10
0x18001095e  mov     [rsp+130h+var_108], rdx
0x180010963  mov     dword ptr [rsp+130h+var_110], r8d
0x180010968  mov     r9, rdi
0x18001096b  mov     rcx, [rcx+10h]
0x18001096f  call    WPP_SF_SDP
0x180010974  mov     edx, 8007065Dh; int
0x180010979  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18001097e  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180010983  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18001098a  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18001098f  call    _CxxThrowException_0
0x180010995  cmp     r10, rdx
0x180010998  jnz     short loc_1800109B4
0x18001099a  mov     qword ptr [rbx+18h], 7
0x1800109a2  mov     qword ptr [rbx+10h], 0
0x1800109aa  xor     eax, eax
0x1800109ac  mov     [rbx], ax
0x1800109af  jmp     loc_180010A74
0x1800109b4  mov     r9, rdx
0x1800109b7  sub     r9, r10
0x1800109ba  test    r9b, 1
0x1800109be  jz      short loc_180010A0F
0x1800109c0  lea     rax, WPP_GLOBAL_Control
0x1800109c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109ce  cmp     rcx, rax
0x1800109d1  jz      short loc_1800109EE
0x1800109d3  cmp     byte ptr [rcx+19h], 2
0x1800109d7  jb      short loc_1800109EE
0x1800109d9  mov     edx, 1Eh
0x1800109de  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x1800109e5  mov     rcx, [rcx+10h]
0x1800109e9  call    WPP_SF_P
0x1800109ee  mov     edx, 8007000Dh; int
0x1800109f3  lea     rcx, [rsp+130h+pExceptionObject]; this
0x1800109f8  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800109fd  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180010a04  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180010a09  call    _CxxThrowException_0
0x180010a0f  lea     r8, [rdx-1]
0x180010a13  cmp     byte ptr [r8], 0
0x180010a17  jz      short loc_180010A68
0x180010a19  lea     rax, WPP_GLOBAL_Control
0x180010a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a27  cmp     rcx, rax
0x180010a2a  jz      short loc_180010A47
0x180010a2c  cmp     byte ptr [rcx+19h], 2
0x180010a30  jb      short loc_180010A47
0x180010a32  mov     edx, 1Fh
0x180010a37  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x180010a3e  mov     rcx, [rcx+10h]
0x180010a42  call    WPP_SF_
0x180010a47  mov     edx, 8007000Dh; int
0x180010a4c  lea     rcx, [rsp+130h+pExceptionObject]; this
0x180010a51  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180010a56  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180010a5d  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180010a62  call    _CxxThrowException_0
0x180010a68  mov     rdx, r10
0x180010a6b  mov     rcx, rbx
0x180010a6e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x180010a73  nop
0x180010a74  lea     rcx, [rsp+130h+var_F8]
0x180010a79  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180010a7e  mov     rax, rbx
0x180010a81  lea     r11, [rsp+130h+var_s0]
0x180010a89  mov     rbx, [r11+10h]
0x180010a8d  mov     rdi, [r11+18h]
0x180010a91  mov     rsp, r11
0x180010a94  pop     rbp
0x180010a95  retn
```
