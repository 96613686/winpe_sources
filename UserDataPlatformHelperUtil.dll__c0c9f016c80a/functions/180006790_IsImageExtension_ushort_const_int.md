# IsImageExtension(ushort const *,int *)

- ea: `0x180006790`
- end: `0x1800068e7`
- name: `?IsImageExtension@@YAJPEBGPEAH@Z`
- size: `343`
- prototype: `__int64 __fastcall(LPCWSTR pszFile, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800017c4`
- `0x1800017e4`
- `0x180001854`
- `0x180003ec0`
- `0x18000439c`
- `0x1800061e0`
- `0x180006790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800067e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000683d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006850`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000683d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006850`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067fe`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x18000682c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x18000682c`

## pseudocode

```c
__int64 __fastcall IsImageExtension(LPCWSTR pszFile, int *a2)
{
  __int64 v4; // rbx
  const WCHAR *v5; // rdx
  int SupportedImageFileExtensions; // ebx
  int v8; // eax

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180011A18 > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&dword_180011A18);
    if ( dword_180011A18 == -1 )
    {
      atexit(IsImageExtension_::_2_::_dynamic_atexit_destructor_for__s_imageExtensions__);
      Init_thread_footer(&dword_180011A18);
    }
  }
  if ( dword_180011A1C > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&dword_180011A1C);
    if ( dword_180011A1C == -1 )
    {
      v8 = ATL::CComCriticalSection::Init(&stru_180011A20);
      if ( v8 < 0 )
        ATL::AtlThrowImpl(v8);
      atexit(IsImageExtension_::_2_::_dynamic_atexit_destructor_for__s_imageExtensionsLock__);
      Init_thread_footer(&dword_180011A1C);
    }
  }
  EnterCriticalSection(&stru_180011A20);
  v5 = (const WCHAR *)hMem;
  if ( hMem )
  {
    if ( *(_WORD *)hMem )
      goto LABEL_8;
    LocalFree(hMem);
  }
  hMem = 0;
  SupportedImageFileExtensions = GetSupportedImageFileExtensions((unsigned __int16 **)&hMem);
  if ( SupportedImageFileExtensions < 0 )
  {
LABEL_10:
    LeaveCriticalSection(&stru_180011A20);
    return (unsigned int)SupportedImageFileExtensions;
  }
  v5 = (const WCHAR *)hMem;
LABEL_8:
  if ( pszFile )
  {
    *a2 = PathMatchSpecW(pszFile, v5);
    SupportedImageFileExtensions = 0;
    goto LABEL_10;
  }
  *a2 = 0;
  LeaveCriticalSection(&stru_180011A20);
  return 0;
}

```

## disassembly

```asm
0x180006790  push    rbx
0x180006792  push    rbp
0x180006793  push    rsi
0x180006794  push    rdi
0x180006795  push    r15
0x180006797  sub     rsp, 20h
0x18000679b  mov     rax, gs:58h
0x1800067a4  mov     rdi, rdx
0x1800067a7  mov     r8d, cs:_tls_index
0x1800067ae  mov     rsi, rcx
0x1800067b1  mov     r15d, 4
0x1800067b7  mov     rbx, [rax+r8*8]
0x1800067bb  mov     eax, [rbx+r15]
0x1800067bf  cmp     cs:dword_180011A18, eax
0x1800067c5  jg      loc_180006880
0x1800067cb  mov     eax, [rbx+r15]
0x1800067cf  xor     ebp, ebp
0x1800067d1  cmp     cs:dword_180011A1C, eax
0x1800067d7  jg      loc_1800068B6
0x1800067dd  lea     rcx, stru_180011A20; lpCriticalSection
0x1800067e4  call    cs:__imp_EnterCriticalSection
0x1800067ea  mov     rdx, cs:hMem
0x1800067f1  test    rdx, rdx
0x1800067f4  jz      short loc_180006804
0x1800067f6  cmp     [rdx], bp
0x1800067f9  jnz     short loc_180006824
0x1800067fb  mov     rcx, rdx; hMem
0x1800067fe  call    cs:__imp_LocalFree
0x180006804  lea     rcx, hMem; unsigned __int16 **
0x18000680b  mov     cs:hMem, rbp
0x180006812  call    ?GetSupportedImageFileExtensions@@YAJPEAPEAG@Z; GetSupportedImageFileExtensions(ushort * *)
0x180006817  mov     ebx, eax
0x180006819  test    eax, eax
0x18000681b  js      short loc_180006836
0x18000681d  mov     rdx, cs:hMem; pszSpec
0x180006824  test    rsi, rsi
0x180006827  jz      short loc_180006847
0x180006829  mov     rcx, rsi; pszFile
0x18000682c  call    cs:__imp_PathMatchSpecW
0x180006832  mov     [rdi], eax
0x180006834  mov     ebx, ebp
0x180006836  lea     rcx, stru_180011A20; lpCriticalSection
0x18000683d  call    cs:__imp_LeaveCriticalSection
0x180006843  mov     eax, ebx
0x180006845  jmp     short loc_180006858
0x180006847  lea     rcx, stru_180011A20; lpCriticalSection
0x18000684e  mov     [rdi], ebp
0x180006850  call    cs:__imp_LeaveCriticalSection
0x180006856  xor     eax, eax
0x180006858  add     rsp, 20h
0x18000685c  pop     r15
0x18000685e  pop     rdi
0x18000685f  pop     rsi
0x180006860  pop     rbp
0x180006861  pop     rbx
0x180006862  retn
0x180006863  lea     rcx, _IsImageExtension____2____dynamic_atexit_destructor_for__s_imageExtensionsLock__; void (__cdecl *)()
0x18000686a  call    atexit
0x18000686f  lea     rcx, dword_180011A1C
0x180006876  call    _Init_thread_footer
0x18000687b  jmp     loc_1800067DD
0x180006880  lea     rcx, dword_180011A18
0x180006887  call    _Init_thread_header
0x18000688c  cmp     cs:dword_180011A18, 0FFFFFFFFh
0x180006893  jnz     loc_1800067CB
0x180006899  lea     rcx, _IsImageExtension____2____dynamic_atexit_destructor_for__s_imageExtensions__; void (__cdecl *)()
0x1800068a0  call    atexit
0x1800068a5  lea     rcx, dword_180011A18
0x1800068ac  call    _Init_thread_footer
0x1800068b1  jmp     loc_1800067CB
0x1800068b6  lea     rcx, dword_180011A1C
0x1800068bd  call    _Init_thread_header
0x1800068c2  cmp     cs:dword_180011A1C, 0FFFFFFFFh
0x1800068c9  jnz     loc_1800067DD
0x1800068cf  lea     rcx, stru_180011A20; this
0x1800068d6  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800068db  test    eax, eax
0x1800068dd  jns     short loc_180006863
0x1800068df  mov     ecx, eax; int
0x1800068e1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
