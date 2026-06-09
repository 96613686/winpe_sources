# DelNodeRunDLL32A(HWND__ *,HINSTANCE__ *,char const *,int)

- ea: `0x180005660`
- end: `0x1800056bc`
- name: `?DelNodeRunDLL32A@@YAJPEAUHWND__@@PEAUHINSTANCE__@@PEBDH@Z`
- size: `92`
- prototype: `HRESULT __stdcall(HWND hwnd, HINSTANCE hInstance, LPSTR pszParms, INT nShow)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180005660`
- `0x18000b1d0`
- `0x1800173a0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800056ab`
- `KERNEL32!LocalFree` at `0x1800056ab`

## pseudocode

```c
HRESULT __stdcall DelNodeRunDLL32A(HWND hwnd, HINSTANCE hInstance, LPSTR pszParms, INT nShow)
{
  HRESULT v7; // ebx

  v7 = -2147467259;
  if ( (int)ThunkToUnicode(pszParms) >= 0 )
    v7 = DelNodeRunDLL32W(hwnd, hInstance, 0, nShow);
  LocalFree(0);
  return v7;
}

```

## disassembly

```asm
0x180005660  push    rbx; DelNodeRunDLL32
0x180005662  push    rbp
0x180005663  push    rsi
0x180005664  push    rdi
0x180005665  sub     rsp, 38h
0x180005669  mov     rsi, rdx
0x18000566c  mov     [rsp+58h+pszParms], 0
0x180005675  mov     rbp, rcx
0x180005678  lea     rdx, [rsp+58h+pszParms]
0x18000567d  mov     rcx, r8; lpMultiByteStr
0x180005680  mov     edi, r9d
0x180005683  mov     ebx, 80004005h
0x180005688  call    ThunkToUnicode
0x18000568d  test    eax, eax
0x18000568f  js      short loc_1800056A6
0x180005691  mov     r8, [rsp+58h+pszParms]; pszParms
0x180005696  mov     r9d, edi; nShow
0x180005699  mov     rdx, rsi; hInstance
0x18000569c  mov     rcx, rbp; hwnd
0x18000569f  call    DelNodeRunDLL32W
0x1800056a4  mov     ebx, eax
0x1800056a6  mov     rcx, [rsp+58h+pszParms]; hMem
0x1800056ab  call    cs:__imp_LocalFree
0x1800056b1  mov     eax, ebx
0x1800056b3  add     rsp, 38h
0x1800056b7  pop     rdi
0x1800056b8  pop     rsi
0x1800056b9  pop     rbp
0x1800056ba  pop     rbx
0x1800056bb  retn
```
