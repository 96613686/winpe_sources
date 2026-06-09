# AuthHostWebInstance::OnNavigateError(IHTMLWindow2 *,IUri *,ushort const *,ulong,IWinInetHttpInfo *,WebPlatformNavigationDataFlags,int *,IUri * *)

- ea: `0x14000aa60`
- end: `0x14000abce`
- name: `?OnNavigateError@AuthHostWebInstance@@UEAAJPEAUIHTMLWindow2@@PEAUIUri@@PEBGKPEAUIWinInetHttpInfo@@W4WebPlatformNavigationDataFlags@@PEAHPEAPEAU3@@Z`
- size: `366`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140002c98`
- `0x14000429c`
- `0x14000aa60`
- `0x14000b840`
- `0x14000c01c`
- `0x14000c2dc`
- `0x14000c934`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000abb3`
- `OLEAUT32!__imp_SysFreeString` at `0x14000abb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthHostWebInstance::OnNavigateError(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        _DWORD *a8,
        _QWORD *a9)
{
  int v11; // eax
  unsigned int v12; // edi
  const unsigned __int16 *v13; // rsi
  char v14; // al
  int v15; // edx
  int v16; // r8d
  unsigned int v17; // ebx
  BSTR bstrString; // [rsp+60h] [rbp+18h] BYREF

  bstrString = 0;
  *a9 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 56LL))(a3, &bstrString);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v13 = bstrString;
    v14 = IsTopWindow(a2);
    v17 = a5;
    if ( v14 || a5 != -2146695933 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 7), v15, v16, (_DWORD)v13, a5, a5);
      }
      TraceWindow(a2);
      *a8 = 1;
      AuthHostWebInstance::TerminateNavigate((AuthHostWebInstance *)(a1 - 8), v13, v17);
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, v13);
      }
      v12 = 0;
      *a8 = 0;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      40,
      &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
      (unsigned int)v11);
  }
  SysFreeString(bstrString);
  return v12;
}

```

## disassembly

```asm
0x14000aa60  mov     r11, rsp
0x14000aa63  mov     [r11+8], rbx
0x14000aa67  mov     [r11+10h], rbp
0x14000aa6b  push    rsi
0x14000aa6c  push    rdi
0x14000aa6d  push    r14
0x14000aa6f  sub     rsp, 30h
0x14000aa73  mov     rbp, rdx
0x14000aa76  mov     r14, rcx
0x14000aa79  mov     qword ptr [r11+18h], 0
0x14000aa81  mov     rax, [rsp+48h+arg_40]
0x14000aa89  mov     qword ptr [rax], 0
0x14000aa90  mov     rax, [r8]
0x14000aa93  lea     rdx, [r11+18h]
0x14000aa97  mov     rcx, r8
0x14000aa9a  mov     rax, [rax+38h]
0x14000aa9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aaa3  mov     edi, eax
0x14000aaa5  test    eax, eax
0x14000aaa7  jns     short loc_14000AAF3
0x14000aaa9  lea     rcx, WPP_GLOBAL_Control
0x14000aab0  mov     r10, cs:WPP_GLOBAL_Control
0x14000aab7  cmp     r10, rcx
0x14000aaba  jz      loc_14000ABAE
0x14000aac0  test    byte ptr [r10+44h], 4
0x14000aac5  jz      loc_14000ABAE
0x14000aacb  cmp     byte ptr [r10+41h], 5
0x14000aad0  jb      loc_14000ABAE
0x14000aad6  mov     edx, 28h ; '('
0x14000aadb  mov     r9d, eax
0x14000aade  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000aae5  mov     rcx, [r10+38h]
0x14000aae9  call    WPP_SF_d
0x14000aaee  jmp     loc_14000ABAE
0x14000aaf3  mov     rsi, [rsp+48h+bstrString]
0x14000aaf8  mov     rcx, rbp
0x14000aafb  call    _IsTopWindow
0x14000ab00  mov     ebx, [rsp+48h+arg_20]
0x14000ab04  test    al, al
0x14000ab06  jnz     short loc_14000AB55
0x14000ab08  cmp     ebx, 800C0503h
0x14000ab0e  jnz     short loc_14000AB55
0x14000ab10  lea     rcx, WPP_GLOBAL_Control
0x14000ab17  mov     rax, cs:WPP_GLOBAL_Control
0x14000ab1e  cmp     rax, rcx
0x14000ab21  jz      short loc_14000AB47
0x14000ab23  test    byte ptr [rax+44h], 4
0x14000ab27  jz      short loc_14000AB47
0x14000ab29  cmp     byte ptr [rax+41h], 4
0x14000ab2d  jb      short loc_14000AB47
0x14000ab2f  mov     edx, 29h ; ')'
0x14000ab34  mov     r9, rsi
0x14000ab37  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000ab3e  mov     rcx, [rax+38h]
0x14000ab42  call    WPP_SF_S
0x14000ab47  xor     edi, edi
0x14000ab49  mov     rax, [rsp+48h+arg_38]
0x14000ab51  mov     [rax], edi
0x14000ab53  jmp     short loc_14000ABAE
0x14000ab55  lea     rcx, WPP_GLOBAL_Control
0x14000ab5c  mov     rax, cs:WPP_GLOBAL_Control
0x14000ab63  cmp     rax, rcx
0x14000ab66  jz      short loc_14000AB88
0x14000ab68  test    byte ptr [rax+44h], 4
0x14000ab6c  jz      short loc_14000AB88
0x14000ab6e  cmp     byte ptr [rax+41h], 2
0x14000ab72  jb      short loc_14000AB88
0x14000ab74  mov     [rsp+48h+var_20], ebx
0x14000ab78  mov     [rsp+48h+var_28], ebx
0x14000ab7c  mov     r9, rsi
0x14000ab7f  mov     rcx, [rax+38h]
0x14000ab83  call    WPP_SF_SDd
0x14000ab88  mov     rcx, rbp
0x14000ab8b  call    _TraceWindow
0x14000ab90  mov     rax, [rsp+48h+arg_38]
0x14000ab98  mov     dword ptr [rax], 1
0x14000ab9e  lea     rcx, [r14-8]; this
0x14000aba2  mov     r8d, ebx; unsigned int
0x14000aba5  mov     rdx, rsi; unsigned __int16 *
0x14000aba8  call    ?TerminateNavigate@AuthHostWebInstance@@AEAAXPEBGK@Z; AuthHostWebInstance::TerminateNavigate(ushort const *,ulong)
0x14000abad  nop
0x14000abae  mov     rcx, [rsp+48h+bstrString]; bstrString
0x14000abb3  call    cs:__imp_SysFreeString
0x14000abb9  mov     eax, edi
0x14000abbb  mov     rbx, [rsp+48h+arg_0]
0x14000abc0  mov     rbp, [rsp+48h+arg_8]
0x14000abc5  add     rsp, 30h
0x14000abc9  pop     r14
0x14000abcb  pop     rdi
0x14000abcc  pop     rsi
0x14000abcd  retn
```
