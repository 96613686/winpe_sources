# REExtendedRegisterClass(void)

- ea: `0x180073800`
- end: `0x180073908`
- name: `?REExtendedRegisterClass@@YAHXZ`
- size: `264`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180023208`
- `0x180073800`

## string_xrefs

- `0x1800738b8`: `REComboBox20W`

## pseudocode

```c
__int64 REExtendedRegisterClass(void)
{
  __int64 result; // rax
  __m128i si128; // xmm6
  bool v2; // zf
  WNDCLASSW WndClass; // [rsp+20h] [rbp-60h] BYREF

  result = CW32System::_fRegisteredXBox;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  *(&WndClass.style + 1) = 0;
  if ( (CW32System::_fRegisteredXBox & 1) == 0 )
  {
    WndClass.style = 16520;
    WndClass.lpfnWndProc = (WNDPROC)RichListBoxWndProc;
    WndClass.hInstance = hinstRE;
    WndClass.cbClsExtra = 0;
    WndClass.lpszClassName = aRelistbox20w_1;
    WndClass.cbWndExtra = 8;
    *(_OWORD *)&WndClass.hIcon = 0;
    *(__m128i *)&WndClass.hbrBackground = si128;
    v2 = CW32System::RegisterREClass(&WndClass, 0, 0) == 0;
    result = CW32System::_fRegisteredXBox;
    if ( !v2 )
    {
      result = CW32System::_fRegisteredXBox | 1;
      CW32System::_fRegisteredXBox |= 1u;
    }
  }
  if ( (result & 2) == 0 )
  {
    WndClass.style = 16523;
    WndClass.lpfnWndProc = (WNDPROC)RichComboBoxWndProc;
    WndClass.hInstance = hinstRE;
    WndClass.cbClsExtra = 0;
    WndClass.lpszClassName = aRecombobox20w;
    WndClass.cbWndExtra = 8;
    *(_OWORD *)&WndClass.hIcon = 0;
    *(__m128i *)&WndClass.hbrBackground = si128;
    v2 = CW32System::RegisterREClass(&WndClass, 0, 0) == 0;
    result = CW32System::_fRegisteredXBox;
    if ( !v2 )
    {
      result = CW32System::_fRegisteredXBox | 2;
      CW32System::_fRegisteredXBox |= 2u;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180073800  mov     [rsp-8+arg_0], rbx
0x180073805  push    rbp
0x180073806  mov     rbp, rsp
0x180073809  sub     rsp, 80h
0x180073810  mov     eax, cs:?_fRegisteredXBox@CW32System@@2IA; uint CW32System::_fRegisteredXBox
0x180073816  xor     ebx, ebx
0x180073818  movaps  [rsp+80h+var_10], xmm6
0x18007381d  movdqa  xmm6, cs:__xmm@00000000000000000000000000000006
0x180073825  mov     dword ptr [rbp+WndClass+4], ebx
0x180073828  test    al, 1
0x18007382a  jnz     short loc_18007388D
0x18007382c  lea     rax, ?RichListBoxWndProc@@YA_JPEAUHWND__@@I_K_J@Z; RichListBoxWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180073833  mov     [rbp+WndClass.style], 4088h
0x18007383a  mov     [rbp+WndClass.lpfnWndProc], rax
0x18007383e  lea     rcx, [rbp+WndClass]; lpWndClass
0x180073842  mov     rax, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hinstRE
0x180073849  xorps   xmm0, xmm0
0x18007384c  mov     [rbp+WndClass.hInstance], rax
0x180073850  xor     r8d, r8d; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x180073853  lea     rax, aRelistbox20w_1; "REListBox20W"
0x18007385a  mov     [rbp+WndClass.cbClsExtra], ebx
0x18007385d  xor     edx, edx; lpString
0x18007385f  mov     [rbp+WndClass.lpszClassName], rax
0x180073863  mov     [rbp+WndClass.cbWndExtra], 8
0x18007386a  movdqa  xmmword ptr [rbp+WndClass.hIcon], xmm0
0x18007386f  movdqa  xmmword ptr [rbp+WndClass.hbrBackground], xmm6
0x180073874  call    ?RegisterREClass@CW32System@@SAGPEBUtagWNDCLASSW@@PEBDP6A_JPEAUHWND__@@I_K_J@Z@Z; CW32System::RegisterREClass(tagWNDCLASSW const *,char const *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64))
0x180073879  test    ax, ax
0x18007387c  mov     eax, cs:?_fRegisteredXBox@CW32System@@2IA; uint CW32System::_fRegisteredXBox
0x180073882  jz      short loc_18007388D
0x180073884  or      eax, 1
0x180073887  mov     cs:?_fRegisteredXBox@CW32System@@2IA, eax; uint CW32System::_fRegisteredXBox
0x18007388d  test    al, 2
0x18007388f  jnz     short loc_1800738F2
0x180073891  lea     rax, ?RichComboBoxWndProc@@YA_JPEAUHWND__@@I_K_J@Z; RichComboBoxWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180073898  mov     [rbp+WndClass.style], 408Bh
0x18007389f  mov     [rbp+WndClass.lpfnWndProc], rax
0x1800738a3  lea     rcx, [rbp+WndClass]; lpWndClass
0x1800738a7  mov     rax, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hinstRE
0x1800738ae  xorps   xmm0, xmm0
0x1800738b1  mov     [rbp+WndClass.hInstance], rax
0x1800738b5  xor     r8d, r8d; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x1800738b8  lea     rax, aRecombobox20w; "REComboBox20W"
0x1800738bf  mov     [rbp+WndClass.cbClsExtra], ebx
0x1800738c2  xor     edx, edx; lpString
0x1800738c4  mov     [rbp+WndClass.lpszClassName], rax
0x1800738c8  mov     [rbp+WndClass.cbWndExtra], 8
0x1800738cf  movdqa  xmmword ptr [rbp+WndClass.hIcon], xmm0
0x1800738d4  movdqa  xmmword ptr [rbp+WndClass.hbrBackground], xmm6
0x1800738d9  call    ?RegisterREClass@CW32System@@SAGPEBUtagWNDCLASSW@@PEBDP6A_JPEAUHWND__@@I_K_J@Z@Z; CW32System::RegisterREClass(tagWNDCLASSW const *,char const *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64))
0x1800738de  test    ax, ax
0x1800738e1  mov     eax, cs:?_fRegisteredXBox@CW32System@@2IA; uint CW32System::_fRegisteredXBox
0x1800738e7  jz      short loc_1800738F2
0x1800738e9  or      eax, 2
0x1800738ec  mov     cs:?_fRegisteredXBox@CW32System@@2IA, eax; uint CW32System::_fRegisteredXBox
0x1800738f2  mov     rbx, [rsp+80h+arg_0]
0x1800738fa  movaps  xmm6, [rsp+80h+var_10]
0x1800738ff  add     rsp, 80h
0x180073906  pop     rbp
0x180073907  retn
```
