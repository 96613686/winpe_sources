# AuthHostWebInstance::OnNavigateCompleted(IHTMLWindow2 *,IUri *,WebPlatformNavigationDataFlags)

- ea: `0x14000a950`
- end: `0x14000aa53`
- name: `?OnNavigateCompleted@AuthHostWebInstance@@UEAAJPEAUIHTMLWindow2@@PEAUIUri@@W4WebPlatformNavigationDataFlags@@@Z`
- size: `259`
- prototype: `int __high(struct IHTMLWindow2 *, struct IUri *, enum WebPlatformNavigationDataFlags)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140002c98`
- `0x14000429c`
- `0x140009988`
- `0x14000a950`
- `0x14000c2dc`
- `0x14000c3dc`
- `0x140014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14000aa42`
- `OLEAUT32!__imp_SysFreeString` at `0x14000aa42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AuthHostWebInstance::OnNavigateCompleted(__int64 a1, struct IHTMLWindow2 *a2, __int64 a3)
{
  int v5; // eax
  unsigned int v6; // esi
  wchar_t *v7; // rbx
  __int64 v8; // rcx
  BSTR bstrString; // [rsp+60h] [rbp+18h] BYREF

  bstrString = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 56LL))(a3, &bstrString);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = bstrString;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, bstrString);
    }
    TraceWindow(a2);
    if ( (unsigned int)(*(_DWORD *)(a1 + 124) - 1) <= 1 && (Microsoft_Windows_WebAuthEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v8, (const EVENT_DESCRIPTOR *)NavigateCompleteEvent, v7);
    AuthHostWebInstance::IsTerminateNavigateUrlReturnWindowTitle((AuthHostWebInstance *)(a1 - 8), a2, v7);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      17,
      &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
      (unsigned int)v5);
  }
  SysFreeString(bstrString);
  return v6;
}

```

## disassembly

```asm
0x14000a950  push    rbx
0x14000a952  push    rbp
0x14000a953  push    rsi
0x14000a954  push    rdi
0x14000a955  sub     rsp, 28h
0x14000a959  mov     rbp, rdx
0x14000a95c  mov     rdi, rcx
0x14000a95f  mov     [rsp+48h+bstrString], 0
0x14000a968  mov     rax, [r8]
0x14000a96b  lea     rdx, [rsp+48h+bstrString]
0x14000a970  mov     rcx, r8
0x14000a973  mov     rax, [rax+38h]
0x14000a977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a97c  mov     esi, eax
0x14000a97e  test    eax, eax
0x14000a980  jns     short loc_14000A9C7
0x14000a982  lea     rdx, WPP_GLOBAL_Control
0x14000a989  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a990  cmp     rcx, rdx
0x14000a993  jz      loc_14000AA3D
0x14000a999  test    byte ptr [rcx+44h], 4
0x14000a99d  jz      loc_14000AA3D
0x14000a9a3  cmp     byte ptr [rcx+41h], 5
0x14000a9a7  jb      loc_14000AA3D
0x14000a9ad  mov     edx, 11h
0x14000a9b2  mov     r9d, eax
0x14000a9b5  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a9bc  mov     rcx, [rcx+38h]
0x14000a9c0  call    WPP_SF_d
0x14000a9c5  jmp     short loc_14000AA3D
0x14000a9c7  mov     rbx, [rsp+48h+bstrString]
0x14000a9cc  lea     rdx, WPP_GLOBAL_Control
0x14000a9d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a9da  cmp     rcx, rdx
0x14000a9dd  jz      short loc_14000AA03
0x14000a9df  test    byte ptr [rcx+44h], 4
0x14000a9e3  jz      short loc_14000AA03
0x14000a9e5  cmp     byte ptr [rcx+41h], 5
0x14000a9e9  jb      short loc_14000AA03
0x14000a9eb  mov     edx, 12h
0x14000a9f0  mov     r9, rbx
0x14000a9f3  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000a9fa  mov     rcx, [rcx+38h]
0x14000a9fe  call    WPP_SF_S
0x14000aa03  mov     rcx, rbp
0x14000aa06  call    _TraceWindow
0x14000aa0b  mov     eax, [rdi+7Ch]
0x14000aa0e  dec     eax
0x14000aa10  cmp     eax, 1
0x14000aa13  ja      short loc_14000AA2D
0x14000aa15  test    cs:Microsoft_Windows_WebAuthEnableBits, 1
0x14000aa1c  jz      short loc_14000AA2D
0x14000aa1e  mov     r8, rbx
0x14000aa21  lea     rdx, NavigateCompleteEvent
0x14000aa28  call    McTemplateU0z_EventWriteTransfer
0x14000aa2d  mov     r8, rbx; String1
0x14000aa30  mov     rdx, rbp; struct IHTMLWindow2 *
0x14000aa33  lea     rcx, [rdi-8]; this
0x14000aa37  call    ?IsTerminateNavigateUrlReturnWindowTitle@AuthHostWebInstance@@AEAAXPEAUIHTMLWindow2@@PEBG@Z; AuthHostWebInstance::IsTerminateNavigateUrlReturnWindowTitle(IHTMLWindow2 *,ushort const *)
0x14000aa3c  nop
0x14000aa3d  mov     rcx, [rsp+48h+bstrString]; bstrString
0x14000aa42  call    cs:__imp_SysFreeString
0x14000aa48  mov     eax, esi
0x14000aa4a  add     rsp, 28h
0x14000aa4e  pop     rdi
0x14000aa4f  pop     rsi
0x14000aa50  pop     rbp
0x14000aa51  pop     rbx
0x14000aa52  retn
```
