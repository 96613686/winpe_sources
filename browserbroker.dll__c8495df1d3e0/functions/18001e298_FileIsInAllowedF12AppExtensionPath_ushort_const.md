# _FileIsInAllowedF12AppExtensionPath(ushort const *)

- ea: `0x18001e298`
- end: `0x18001e3b0`
- name: `?_FileIsInAllowedF12AppExtensionPath@@YA_NPEBG@Z`
- size: `280`
- prototype: `char __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18001e0b8`

## callees

- `0x180003170`
- `0x180007018`
- `0x18001a6dc`
- `0x18001e298`
- `0x18001e7f0`
- `0x18001e840`
- `0x18001e850`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e378`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001e378`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18001e2f3`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18001e2f3`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x18001e32b`
- `api-ms-win-core-path-l1-1-0!PathCchStripPrefix` at `0x18001e32b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001e2c2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001e2c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall _FileIsInAllowedF12AppExtensionPath(PCWSTR pszPathIn)
{
  char v2; // si
  WCHAR *v3; // rdi
  size_t v4; // r14
  __int64 v5; // rbp
  __int64 i; // rbx
  int v7; // edx
  const WCHAR *v8; // r8
  size_t cchPath; // [rsp+68h] [rbp+10h] BYREF
  WCHAR *v11; // [rsp+70h] [rbp+18h] BYREF

  v2 = 0;
  if ( InitOnceExecuteOnce(&LocalFileBroker::g_InitOnce, PopulateAllowedF12ExtensionsPaths, 0, 0) )
  {
    v11 = (WCHAR *)operator new[](0x10000u);
    v3 = v11;
    if ( PathCchCanonicalizeEx(v11, 0x8000u, pszPathIn, 0x21u) >= 0 )
    {
      cchPath = 0;
      if ( (int)StringCchLengthW(v3, 0x7FFFFFFFu, &cchPath) >= 0 )
      {
        v4 = cchPath;
        if ( PathCchStripPrefix(v3, cchPath) >= 0 )
        {
          v5 = std::vector<std::wstring>::_Unchecked_end();
          for ( i = std::vector<std::wstring>::_Unchecked_begin(); i != v5; i += 32 )
          {
            if ( v4 >= *(_QWORD *)(i + 16) )
            {
              if ( (unsigned __int8)std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(
                                      i,
                                      *(unsigned int *)(i + 16)) )
                v8 = *(const WCHAR **)i;
              else
                v8 = (const WCHAR *)i;
              if ( CompareStringOrdinal(v3, v7, v8, v7, 1) == 2 )
                v2 = 1;
            }
          }
        }
      }
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&v11);
  }
  return v2;
}

```

## disassembly

```asm
0x18001e298  mov     [rsp+arg_0], rbx
0x18001e29d  push    rbp
0x18001e29e  push    rsi
0x18001e29f  push    rdi
0x18001e2a0  push    r14
0x18001e2a2  push    r15
0x18001e2a4  sub     rsp, 30h
0x18001e2a8  mov     rbx, rcx
0x18001e2ab  lea     rdx, ?PopulateAllowedF12ExtensionsPaths@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001e2b2  lea     rcx, ?g_InitOnce@LocalFileBroker@@2T_RTL_RUN_ONCE@@A; InitOnce
0x18001e2b9  xor     r9d, r9d; Context
0x18001e2bc  xor     r8d, r8d; Parameter
0x18001e2bf  xor     sil, sil
0x18001e2c2  call    cs:__imp_InitOnceExecuteOnce
0x18001e2c8  test    eax, eax
0x18001e2ca  jz      loc_18001E39C
0x18001e2d0  mov     ecx, 10000h; unsigned __int64
0x18001e2d5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001e2da  mov     r9d, 21h ; '!'; dwFlags
0x18001e2e0  mov     [rsp+58h+arg_10], rax
0x18001e2e5  mov     r8, rbx; pszPathIn
0x18001e2e8  mov     edx, 8000h; cchPathOut
0x18001e2ed  mov     rcx, rax; pszPathOut
0x18001e2f0  mov     rdi, rax
0x18001e2f3  call    cs:__imp_PathCchCanonicalizeEx
0x18001e2f9  test    eax, eax
0x18001e2fb  js      loc_18001E392
0x18001e301  lea     r8, [rsp+58h+cchPath]; unsigned __int64 *
0x18001e306  mov     [rsp+58h+cchPath], 0
0x18001e30f  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001e314  mov     rcx, rdi; unsigned __int16 *
0x18001e317  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e31c  test    eax, eax
0x18001e31e  js      short loc_18001E392
0x18001e320  mov     r14, [rsp+58h+cchPath]
0x18001e325  mov     rcx, rdi; pszPath
0x18001e328  mov     rdx, r14; cchPath
0x18001e32b  call    cs:__imp_PathCchStripPrefix
0x18001e331  test    eax, eax
0x18001e333  js      short loc_18001E392
0x18001e335  call    ?_Unchecked_end@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::vector<std::wstring>::_Unchecked_end(void)
0x18001e33a  mov     rbp, rax
0x18001e33d  call    ?_Unchecked_begin@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::vector<std::wstring>::_Unchecked_begin(void)
0x18001e342  mov     rbx, rax
0x18001e345  cmp     rax, rbp
0x18001e348  jz      short loc_18001E392
0x18001e34a  mov     r15d, 1
0x18001e350  cmp     r14, [rbx+10h]
0x18001e354  jb      short loc_18001E389
0x18001e356  mov     edx, [rbx+10h]
0x18001e359  mov     rcx, rbx
0x18001e35c  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x18001e361  test    al, al
0x18001e363  jz      short loc_18001E36A
0x18001e365  mov     r8, [rbx]
0x18001e368  jmp     short loc_18001E36D
0x18001e36a  mov     r8, rbx; lpString2
0x18001e36d  mov     r9d, edx; cchCount2
0x18001e370  mov     [rsp+58h+bIgnoreCase], r15d; bIgnoreCase
0x18001e375  mov     rcx, rdi; lpString1
0x18001e378  call    cs:__imp_CompareStringOrdinal
0x18001e37e  cmp     eax, 2
0x18001e381  movzx   esi, sil
0x18001e385  cmovz   esi, r15d
0x18001e389  add     rbx, 20h ; ' '
0x18001e38d  cmp     rbx, rbp
0x18001e390  jnz     short loc_18001E350
0x18001e392  lea     rcx, [rsp+58h+arg_10]
0x18001e397  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18001e39c  mov     rbx, [rsp+58h+arg_0]
0x18001e3a1  mov     al, sil
0x18001e3a4  add     rsp, 30h
0x18001e3a8  pop     r15
0x18001e3aa  pop     r14
0x18001e3ac  pop     rdi
0x18001e3ad  pop     rsi
0x18001e3ae  pop     rbp
0x18001e3af  retn
```
