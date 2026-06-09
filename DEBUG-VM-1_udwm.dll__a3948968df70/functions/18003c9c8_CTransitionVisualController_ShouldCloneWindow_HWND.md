# CTransitionVisualController::ShouldCloneWindow(HWND__ *)

- ea: `0x18003c9c8`
- end: `0x18003cb1f`
- name: `?ShouldCloneWindow@CTransitionVisualController@@SA_NPEAUHWND__@@@Z`
- size: `343`
- prototype: `bool __fastcall(HWND hWnd)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18002cbd0`
- `0x18003af34`
- `0x18003db84`
- `0x180061058`
- `0x1800cdc98`
- `0x1800cdef0`

## callees

- `0x18003c9c8`
- `0x18003cb28`
- `0x180095130`
- `0x180095b4c`

## import_xrefs

- `USER32!GetWindowRect` at `0x18003c9ff`
- `USER32!GetWindowRect` at `0x18003c9ff`
- `USER32!GetClassNameW` at `0x18003ca69`
- `USER32!GetClassNameW` at `0x18003ca69`
- `USER32!IsRectEmpty` at `0x18003ca0e`
- `USER32!IsRectEmpty` at `0x18003ca0e`

## pseudocode

```c
char __fastcall CTransitionVisualController::ShouldCloneWindow(HWND hWnd)
{
  char v2; // bl
  CDesktopManager *v4; // rbp
  unsigned int i; // edi
  WCHAR *v6; // rdx
  int v7; // r8d
  int v8; // eax
  __int64 j; // rcx
  WCHAR *v10; // rax
  int v11; // edx
  int v12; // ecx
  struct tagRECT Rect; // [rsp+20h] [rbp-248h] BYREF
  WCHAR ClassName[264]; // [rsp+30h] [rbp-238h] BYREF

  Rect = 0;
  if ( GetWindowRect(hWnd, &Rect) && IsRectEmpty(&Rect) )
    return 0;
  v2 = 1;
  memset_0(ClassName, 0, 0x208u);
  if ( GetClassNameW(hWnd, ClassName, 260) )
  {
    v4 = CDesktopManager::s_pDesktopManagerInstance;
    for ( i = 0; i < 6; ++i )
    {
      if ( CAnimationScheduler::IsWindowCurrentlyAnimating(
             *((CAnimationScheduler **)v4 + 23),
             0,
             dword_1800F2308[4 * i],
             0) )
      {
        v10 = ClassName;
        do
        {
          v11 = *(WCHAR *)((char *)v10 + (char *)(&off_1800F2300)[2 * i] - (char *)ClassName);
          v12 = *v10 - v11;
          if ( v12 )
            break;
          ++v10;
        }
        while ( v11 );
        if ( !v12 )
          return v2;
      }
    }
    for ( j = 0; (unsigned int)j < 0xC; j = (unsigned int)(j + 1) )
    {
      v6 = ClassName;
      do
      {
        v7 = *(WCHAR *)((char *)v6 + (char *)off_1800F2380[j] - (char *)ClassName);
        v8 = *v6 - v7;
        if ( v8 )
          break;
        ++v6;
      }
      while ( v7 );
      if ( !v8 )
        return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18003c9c8  mov     [rsp+arg_8], rbx
0x18003c9cd  mov     [rsp+arg_10], rbp
0x18003c9d2  push    rsi
0x18003c9d3  push    rdi
0x18003c9d4  push    r14
0x18003c9d6  sub     rsp, 250h
0x18003c9dd  mov     rax, cs:__security_cookie
0x18003c9e4  xor     rax, rsp
0x18003c9e7  mov     [rsp+268h+var_28], rax
0x18003c9ef  xorps   xmm0, xmm0
0x18003c9f2  lea     rdx, [rsp+268h+Rect]; lpRect
0x18003c9f7  movups  xmmword ptr [rsp+268h+Rect.left], xmm0
0x18003c9fc  mov     rdi, rcx
0x18003c9ff  call    cs:__imp_GetWindowRect
0x18003ca05  test    eax, eax
0x18003ca07  jz      short loc_18003CA44
0x18003ca09  lea     rcx, [rsp+268h+Rect]; lprc
0x18003ca0e  call    cs:__imp_IsRectEmpty
0x18003ca14  test    eax, eax
0x18003ca16  jz      short loc_18003CA44
0x18003ca18  xor     bl, bl
0x18003ca1a  mov     al, bl
0x18003ca1c  mov     rcx, [rsp+268h+var_28]
0x18003ca24  xor     rcx, rsp; StackCookie
0x18003ca27  call    __security_check_cookie
0x18003ca2c  lea     r11, [rsp+268h+var_18]
0x18003ca34  mov     rbx, [r11+28h]
0x18003ca38  mov     rbp, [r11+30h]
0x18003ca3c  mov     rsp, r11
0x18003ca3f  pop     r14
0x18003ca41  pop     rdi
0x18003ca42  pop     rsi
0x18003ca43  retn
0x18003ca44  xor     edx, edx; Val
0x18003ca46  lea     rcx, [rsp+268h+ClassName]; void *
0x18003ca4b  mov     r8d, 208h; Size
0x18003ca51  mov     ebx, 1
0x18003ca56  call    memset_0
0x18003ca5b  mov     r8d, 104h; nMaxCount
0x18003ca61  lea     rdx, [rsp+268h+ClassName]; lpClassName
0x18003ca66  mov     rcx, rdi; hWnd
0x18003ca69  call    cs:__imp_GetClassNameW
0x18003ca6f  test    eax, eax
0x18003ca71  jz      short loc_18003CA1A
0x18003ca73  mov     rbp, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18003ca7a  lea     r14, __ImageBase
0x18003ca81  xor     edi, edi
0x18003ca83  cmp     edi, 6
0x18003ca86  jnb     loc_18003CB1B
0x18003ca8c  mov     rcx, [rbp+0B8h]; this
0x18003ca93  xor     r9d, r9d; unsigned int
0x18003ca96  mov     esi, edi
0x18003ca98  xor     edx, edx; HWND
0x18003ca9a  add     rsi, rsi
0x18003ca9d  mov     r8d, ds:rva dword_1800F2308[r14+rsi*8]; int
0x18003caa5  call    ?IsWindowCurrentlyAnimating@CAnimationScheduler@@QEAA_NQEAUHWND__@@HK@Z; CAnimationScheduler::IsWindowCurrentlyAnimating(HWND__ * const,int,ulong)
0x18003caaa  test    al, al
0x18003caac  jnz     short loc_18003CAED
0x18003caae  add     edi, ebx
0x18003cab0  jmp     short loc_18003CA83
0x18003cab2  cmp     ecx, 0Ch
0x18003cab5  jnb     loc_18003CA1A
0x18003cabb  mov     r9, ds:rva off_1800F2380[r14+rcx*8]; "#32768" ...
0x18003cac3  lea     rdx, [rsp+268h+ClassName]
0x18003cac8  sub     r9, rdx
0x18003cacb  movzx   eax, word ptr [rdx]
0x18003cace  movzx   r8d, word ptr [rdx+r9]
0x18003cad3  sub     eax, r8d
0x18003cad6  jnz     short loc_18003CAE1
0x18003cad8  add     rdx, 2
0x18003cadc  test    r8d, r8d
0x18003cadf  jnz     short loc_18003CACB
0x18003cae1  test    eax, eax
0x18003cae3  jz      loc_18003CA18
0x18003cae9  add     ecx, ebx
0x18003caeb  jmp     short loc_18003CAB2
0x18003caed  mov     r8, ds:rva off_1800F2300[r14+rsi*8]; "ImmersiveDragVisual" ...
0x18003caf5  lea     rax, [rsp+268h+ClassName]
0x18003cafa  sub     r8, rax
0x18003cafd  movzx   ecx, word ptr [rax]
0x18003cb00  movzx   edx, word ptr [rax+r8]
0x18003cb05  sub     ecx, edx
0x18003cb07  jnz     short loc_18003CB11
0x18003cb09  add     rax, 2
0x18003cb0d  test    edx, edx
0x18003cb0f  jnz     short loc_18003CAFD
0x18003cb11  test    ecx, ecx
0x18003cb13  jz      loc_18003CA1A
0x18003cb19  jmp     short loc_18003CAAE
0x18003cb1b  xor     ecx, ecx
0x18003cb1d  jmp     short loc_18003CAB2
```
