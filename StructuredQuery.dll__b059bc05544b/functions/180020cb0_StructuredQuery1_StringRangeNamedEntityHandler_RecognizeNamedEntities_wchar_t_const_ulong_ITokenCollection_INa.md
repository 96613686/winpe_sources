# StructuredQuery1::StringRangeNamedEntityHandler::RecognizeNamedEntities(wchar_t const *,ulong,ITokenCollection *,INamedEntityCollector *)

- ea: `0x180020cb0`
- end: `0x1800210ac`
- name: `?RecognizeNamedEntities@StringRangeNamedEntityHandler@StructuredQuery1@@UEAAJPEB_WKPEAUITokenCollection@@PEAUINamedEntityCollector@@@Z`
- size: `1020`
- prototype: `__int64 __fastcall(StructuredQuery1::StringRangeNamedEntityHandler *__hidden this, const wchar_t *, unsigned int, struct ITokenCollection *, struct INamedEntityCollector *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180020250`
- `0x1800204f4`
- `0x180020cb0`
- `0x180035e7c`
- `0x18005daf0`
- `0x18005e740`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020f4d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180020f4d`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180020f1b`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180020f1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020e16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020e16`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::StringRangeNamedEntityHandler::RecognizeNamedEntities(
        StructuredQuery1::StringRangeNamedEntityHandler *this,
        const wchar_t *a2,
        int a3,
        struct ITokenCollection *a4,
        struct INamedEntityCollector *a5)
{
  struct ITokenCollectionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *NumberOfTokens)(ITokenCollection *, ULONG *); // rax
  __int64 result; // rax
  wchar_t **v9; // r8
  int v10; // r12d
  const wchar_t *v11; // r13
  __int64 v12; // rbp
  struct ITokenCollectionVtbl *v13; // rax
  wchar_t ***v14; // rdi
  unsigned __int64 v15; // rbx
  __int64 v16; // rsi
  unsigned __int64 v17; // r14
  wchar_t **v18; // rax
  const size_t *v19; // rcx
  unsigned __int64 v20; // rdx
  __int64 v21; // r9
  wchar_t **v22; // rcx
  __int64 v23; // r10
  StructuredQuery1::StringRangeNamedEntityHandler *v24; // r13
  unsigned int i; // ebp
  __int64 v26; // rbx
  __int64 v27; // rax
  unsigned int v28; // esi
  __int64 v29; // r15
  __int64 j; // rdi
  LANGID UserDefaultUILanguage; // ax
  __int64 v32; // r14
  bool v33; // cf
  PCNZWCH lpString2; // [rsp+20h] [rbp-F8h]
  StructuredQuery1 *v35; // [rsp+50h] [rbp-C8h] BYREF
  const wchar_t *v36; // [rsp+58h] [rbp-C0h] BYREF
  void *v37; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+68h] [rbp-B0h] BYREF
  int v39; // [rsp+70h] [rbp-A8h]
  StructuredQuery1::StringRangeNamedEntityHandler *v40; // [rsp+78h] [rbp-A0h]
  struct INamedEntityCollector *v41; // [rsp+80h] [rbp-98h]
  wchar_t v42[32]; // [rsp+90h] [rbp-88h] BYREF

  v41 = a5;
  lpVtbl = a4->lpVtbl;
  v36 = a2;
  v40 = this;
  v39 = a3;
  NumberOfTokens = lpVtbl->NumberOfTokens;
  LODWORD(v35) = 0;
  result = ((__int64 (__fastcall *)(struct ITokenCollection *, StructuredQuery1 **))NumberOfTokens)(a4, &v35);
  if ( (int)result >= 0 )
  {
    v37 = 0;
    v38 = 0;
    if ( is_mul_ok((unsigned int)v35, 8u) )
    {
      result = CTCoAllocPolicy::Alloc((IMalloc *)(unsigned int)v35, 1, 8LL * (unsigned int)v35, &v37);
      v10 = result;
      if ( (int)result >= 0 )
      {
        v11 = v36;
        v12 = 0;
        do
        {
          if ( (unsigned int)v12 >= (unsigned int)v35 )
            break;
          v13 = a4->lpVtbl;
          LODWORD(v36) = 0;
          LODWORD(v38) = 0;
          v14 = (wchar_t ***)((char *)v37 + 8 * v12);
          v10 = ((__int64 (__fastcall *)(struct ITokenCollection *, _QWORD, const wchar_t **, __int64 *, wchar_t ***))v13->GetToken)(
                  a4,
                  (unsigned int)v12,
                  &v36,
                  &v38,
                  v14);
          if ( v10 >= 0 && !*v14 )
          {
            v15 = (unsigned int)v38;
            v16 = (unsigned int)v36;
            *v14 = 0;
            v17 = v15 + 1;
            if ( v15 + 1 >= v15 && is_mul_ok(v17, 2u) )
            {
              v18 = (wchar_t **)CoTaskMemAlloc(2 * v17);
              v10 = -2147024882;
              *v14 = v18;
              if ( v18 )
                v10 = 0;
              if ( v10 >= 0 )
              {
                if ( v18 && v17 <= 0x7FFFFFFF && v15 < 0x7FFFFFFF )
                {
                  v19 = (const size_t *)&v11[v16];
                  if ( !v19 )
                  {
                    v19 = &cchOriginalDestLength;
                    v15 = 0;
                  }
                  v20 = v17;
                  v9 = v18;
                  v21 = 0;
                  do
                  {
                    if ( !v15 )
                      break;
                    if ( !*(_WORD *)v19 )
                      break;
                    *(_WORD *)v9 = *(_WORD *)v19;
                    v19 = (const size_t *)((char *)v19 + 2);
                    v9 = (wchar_t **)((char *)v9 + 2);
                    --v15;
                    ++v21;
                    --v20;
                  }
                  while ( v20 );
                  v22 = (wchar_t **)((char *)v9 - 2);
                  v23 = v21 - 1;
                  if ( v20 )
                  {
                    v22 = v9;
                    v23 = v21;
                  }
                  *(_WORD *)v22 = 0;
                  if ( v20 )
                  {
                    v33 = v17 == v23;
                    v32 = v17 - v23;
                    if ( !v33 && v32 != 1 )
                    {
                      v9 = (wchar_t **)(2 * v32);
                      if ( (unsigned __int64)(2 * v32) > 2 )
                        memset_0((char *)v18 + 2 * v23 + 2, 0, (size_t)v9 - 2);
                    }
                  }
                }
                else
                {
                  *(_WORD *)v18 = 0;
                }
              }
            }
            else
            {
              v10 = -2147024362;
            }
          }
          v12 = (unsigned int)(v12 + 1);
        }
        while ( v10 >= 0 );
        v24 = v40;
        for ( i = 0; v10 >= 0; ++i )
        {
          if ( i >= (unsigned int)v35 )
            break;
          v26 = 0;
          do
          {
            if ( (unsigned int)v26 >= *((_DWORD *)v24 + 7) )
              break;
            v27 = *((_QWORD *)v24 + 4);
            v28 = *(_DWORD *)(v27 + 24 * v26);
            if ( v28 + i <= (unsigned int)v35 )
            {
              v29 = *(_QWORD *)(v27 + 24 * v26 + 8);
              for ( j = 0; (unsigned int)j < v28; j = (unsigned int)(j + 1) )
              {
                UserDefaultUILanguage = GetUserDefaultUILanguage();
                if ( CompareStringW(
                       UserDefaultUILanguage,
                       0x20001u,
                       *((PCNZWCH *)v37 + (unsigned int)j + i),
                       -1,
                       *(PCNZWCH *)(v29 + 8 * j),
                       -1) != 2 )
                  goto LABEL_34;
              }
              LODWORD(lpString2) = v39;
              v10 = StringCchPrintfW(v42, 0x1Eu, L"%lu %lu", (unsigned int)v26, lpString2);
              if ( v10 >= 0 )
                v10 = ((__int64 (__fastcall *)(struct INamedEntityCollector *, _QWORD, _QWORD, _QWORD, unsigned int, _QWORD, wchar_t *, int))v41->lpVtbl->Add)(
                        v41,
                        i,
                        v28 + i,
                        i,
                        v28 + i,
                        *((_QWORD *)v24 + 2),
                        v42,
                        1);
            }
LABEL_34:
            v26 = (unsigned int)(v26 + 1);
          }
          while ( v10 >= 0 );
        }
        StructuredQuery1::ClearStringArray((StructuredQuery1 *)(unsigned int)v35, (LPVOID *)v37, v9);
        return (unsigned int)v10;
      }
    }
    else
    {
      return 2147942934LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180020cb0  push    r13
0x180020cb2  push    r15
0x180020cb4  sub     rsp, 108h
0x180020cbb  mov     rax, cs:__security_cookie
0x180020cc2  xor     rax, rsp
0x180020cc5  mov     [rsp+118h+var_48], rax
0x180020ccd  mov     rax, [rsp+118h+arg_20]
0x180020cd5  mov     r15, r9
0x180020cd8  mov     [rsp+118h+var_98], rax
0x180020ce0  mov     rax, [r9]
0x180020ce3  mov     [rsp+118h+var_C0], rdx
0x180020ce8  lea     rdx, [rsp+118h+var_C8]
0x180020ced  mov     [rsp+118h+var_A0], rcx
0x180020cf2  mov     rcx, r9
0x180020cf5  mov     [rsp+118h+var_A8], r8d
0x180020cfa  mov     rax, [rax+18h]
0x180020cfe  mov     dword ptr [rsp+118h+var_C8], 0
0x180020d06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d0b  test    eax, eax
0x180020d0d  js      loc_180020FAF
0x180020d13  mov     ecx, dword ptr [rsp+118h+var_C8]; void *
0x180020d17  mov     eax, 8
0x180020d1c  mul     rcx
0x180020d1f  mov     [rsp+118h+var_B8], 0
0x180020d28  mov     [rsp+118h+var_B0], 0
0x180020d31  test    rdx, rdx
0x180020d34  jnz     loc_1800210A2
0x180020d3a  lea     r9, [rsp+118h+var_B8]; void **
0x180020d3f  mov     [rsp+118h+var_30], r12
0x180020d47  mov     r8, rax; unsigned __int64
0x180020d4a  mov     edx, 1; unsigned int
0x180020d4f  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180020d54  mov     r12d, eax
0x180020d57  test    eax, eax
0x180020d59  js      loc_180020FA7
0x180020d5f  mov     r13, [rsp+118h+var_C0]
0x180020d64  mov     [rsp+118h+arg_8], rbx
0x180020d6c  mov     [rsp+118h+var_18], rbp
0x180020d74  xor     ebp, ebp
0x180020d76  mov     [rsp+118h+var_20], rsi
0x180020d7e  mov     [rsp+118h+var_28], rdi
0x180020d86  mov     [rsp+118h+var_38], r14
0x180020d8e  xchg    ax, ax
0x180020d90  cmp     ebp, dword ptr [rsp+118h+var_C8]
0x180020d94  jnb     loc_180020EC8
0x180020d9a  mov     rcx, [rsp+118h+var_B8]
0x180020d9f  lea     r9, [rsp+118h+var_B0]
0x180020da4  mov     rax, [r15]
0x180020da7  lea     r8, [rsp+118h+var_C0]
0x180020dac  mov     edx, ebp
0x180020dae  mov     dword ptr [rsp+118h+var_C0], 0
0x180020db6  mov     dword ptr [rsp+118h+var_B0], 0
0x180020dbe  lea     rdi, [rcx+rbp*8]
0x180020dc2  mov     rcx, r15
0x180020dc5  mov     rax, [rax+20h]
0x180020dc9  mov     [rsp+118h+lpString2], rdi
0x180020dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dd3  mov     r12d, eax
0x180020dd6  test    eax, eax
0x180020dd8  js      loc_180020EBD
0x180020dde  cmp     qword ptr [rdi], 0
0x180020de2  jnz     loc_180020EBD
0x180020de8  mov     ebx, dword ptr [rsp+118h+var_B0]
0x180020dec  xor     eax, eax
0x180020dee  mov     esi, dword ptr [rsp+118h+var_C0]
0x180020df2  mov     [rdi], rax
0x180020df5  lea     r14, [rbx+1]
0x180020df9  cmp     r14, rbx
0x180020dfc  jb      loc_180020FCB
0x180020e02  mov     eax, 2
0x180020e07  mul     r14
0x180020e0a  test    rdx, rdx
0x180020e0d  jnz     loc_180020FCB
0x180020e13  mov     rcx, rax; cb
0x180020e16  call    cs:__imp_CoTaskMemAlloc
0x180020e1c  xor     ecx, ecx
0x180020e1e  mov     r12d, 8007000Eh
0x180020e24  test    rax, rax
0x180020e27  mov     [rdi], rax
0x180020e2a  mov     r11, rax
0x180020e2d  cmovnz  r12d, ecx
0x180020e31  test    r12d, r12d
0x180020e34  js      loc_180020EBD
0x180020e3a  test    rax, rax
0x180020e3d  jz      loc_180021097
0x180020e43  cmp     r14, 7FFFFFFFh
0x180020e4a  ja      loc_180021097
0x180020e50  cmp     rbx, 7FFFFFFFh
0x180020e57  jnb     loc_180021097
0x180020e5d  lea     rcx, ds:0[rsi*2]
0x180020e65  add     rcx, r13
0x180020e68  jz      loc_180021010
0x180020e6e  mov     rdx, r14
0x180020e71  mov     r8, r11
0x180020e74  xor     r9d, r9d
0x180020e77  test    rbx, rbx
0x180020e7a  jz      short loc_180020E9C
0x180020e7c  movzx   eax, word ptr [rcx]
0x180020e7f  test    ax, ax
0x180020e82  jz      short loc_180020E9C
0x180020e84  mov     [r8], ax
0x180020e88  add     rcx, 2
0x180020e8c  add     r8, 2
0x180020e90  dec     rbx
0x180020e93  inc     r9
0x180020e96  sub     rdx, 1
0x180020e9a  jnz     short loc_180020E77
0x180020e9c  test    rdx, rdx
0x180020e9f  lea     rcx, [r8-2]
0x180020ea3  lea     r10, [r9-1]
0x180020ea7  cmovnz  rcx, r8
0x180020eab  cmovnz  r10, r9
0x180020eaf  xor     eax, eax
0x180020eb1  mov     [rcx], ax
0x180020eb4  test    rdx, rdx
0x180020eb7  jnz     loc_180020FD6
0x180020ebd  inc     ebp
0x180020ebf  test    r12d, r12d
0x180020ec2  jns     loc_180020D90
0x180020ec8  mov     r13, [rsp+118h+var_A0]
0x180020ecd  xor     ebp, ebp
0x180020ecf  test    r12d, r12d
0x180020ed2  js      loc_180020F6E
0x180020ed8  nop     dword ptr [rax+rax+00000000h]
0x180020ee0  cmp     ebp, dword ptr [rsp+118h+var_C8]
0x180020ee4  jnb     loc_180020F6E
0x180020eea  xor     ebx, ebx
0x180020eec  nop     dword ptr [rax+00h]
0x180020ef0  cmp     ebx, [r13+1Ch]
0x180020ef4  jnb     short loc_180020F63
0x180020ef6  mov     rax, [r13+20h]
0x180020efa  lea     rcx, [rbx+rbx*2]
0x180020efe  mov     esi, [rax+rcx*8]
0x180020f01  lea     r14d, [rsi+rbp]
0x180020f05  cmp     r14d, dword ptr [rsp+118h+var_C8]
0x180020f0a  ja      short loc_180020F5C
0x180020f0c  mov     r15, [rax+rcx*8+8]
0x180020f11  xor     edi, edi
0x180020f13  cmp     edi, esi
0x180020f15  jnb     loc_18002101E
0x180020f1b  call    cs:__imp_GetUserDefaultUILanguage
0x180020f21  mov     [rsp+118h+cchCount2], 0FFFFFFFFh; cchCount2
0x180020f29  lea     r8d, [rdi+rbp]
0x180020f2d  movzx   ecx, ax; Locale
0x180020f30  mov     r9d, 0FFFFFFFFh; cchCount1
0x180020f36  mov     rax, [r15+rdi*8]
0x180020f3a  mov     edx, 20001h; dwCmpFlags
0x180020f3f  mov     [rsp+118h+lpString2], rax; lpString2
0x180020f44  mov     rax, [rsp+118h+var_B8]
0x180020f49  mov     r8, [rax+r8*8]; lpString1
0x180020f4d  call    cs:__imp_CompareStringW
0x180020f53  cmp     eax, 2
0x180020f56  jz      loc_180021009
0x180020f5c  inc     ebx
0x180020f5e  test    r12d, r12d
0x180020f61  jns     short loc_180020EF0
0x180020f63  inc     ebp
0x180020f65  test    r12d, r12d
0x180020f68  jns     loc_180020EE0
0x180020f6e  mov     rdx, [rsp+118h+var_B8]; unsigned int
0x180020f73  mov     ecx, dword ptr [rsp+118h+var_C8]; this
0x180020f77  call    ?ClearStringArray@StructuredQuery1@@YAXKPEAPEA_W@Z; StructuredQuery1::ClearStringArray(ulong,wchar_t * *)
0x180020f7c  mov     r14, [rsp+118h+var_38]
0x180020f84  mov     eax, r12d
0x180020f87  mov     rdi, [rsp+118h+var_28]
0x180020f8f  mov     rsi, [rsp+118h+var_20]
0x180020f97  mov     rbp, [rsp+118h+var_18]
0x180020f9f  mov     rbx, [rsp+118h+arg_8]
0x180020fa7  mov     r12, [rsp+118h+var_30]
0x180020faf  mov     rcx, [rsp+118h+var_48]
0x180020fb7  xor     rcx, rsp; StackCookie
0x180020fba  call    __security_check_cookie
0x180020fbf  add     rsp, 108h
0x180020fc6  pop     r15
0x180020fc8  pop     r13
0x180020fca  retn
0x180020fcb  mov     r12d, 80070216h
0x180020fd1  jmp     loc_180020EBD
0x180020fd6  sub     r14, r10
0x180020fd9  cmp     r14, 1
0x180020fdd  jbe     loc_180020EBD
0x180020fe3  lea     r8, [r14+r14]
0x180020fe7  cmp     r8, 2
0x180020feb  jbe     loc_180020EBD
0x180020ff1  add     r11, 2
0x180020ff5  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180020ff9  xor     edx, edx; Val
0x180020ffb  lea     rcx, [r11+r10*2]; void *
0x180020fff  call    memset_0
0x180021004  jmp     loc_180020EBD
0x180021009  inc     edi
0x18002100b  jmp     loc_180020F13
0x180021010  lea     rcx, cchOriginalDestLength
0x180021017  xor     ebx, ebx
0x180021019  jmp     loc_180020E6E
0x18002101e  mov     eax, [rsp+118h+var_A8]
0x180021022  lea     r8, aLuLu; "%lu %lu"
0x180021029  mov     r9d, ebx
0x18002102c  mov     dword ptr [rsp+118h+lpString2], eax
0x180021030  mov     edx, 1Eh; unsigned __int64
0x180021035  lea     rcx, [rsp+118h+var_88]; wchar_t *
0x18002103d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180021042  mov     r12d, eax
0x180021045  test    eax, eax
0x180021047  js      loc_180020F5C
0x18002104d  mov     r10, [rsp+118h+var_98]
0x180021055  lea     rcx, [rsp+118h+var_88]
0x18002105d  mov     [rsp+118h+var_E0], 1
0x180021065  mov     r9d, ebp
0x180021068  mov     [rsp+118h+var_E8], rcx
0x18002106d  mov     r8d, r14d
0x180021070  mov     rcx, [r13+10h]
0x180021074  mov     edx, ebp
0x180021076  mov     rax, [r10]
0x180021079  mov     qword ptr [rsp+118h+cchCount2], rcx
0x18002107e  mov     rcx, r10
0x180021081  mov     dword ptr [rsp+118h+lpString2], r14d
0x180021086  mov     rax, [rax+18h]
0x18002108a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002108f  mov     r12d, eax
0x180021092  jmp     loc_180020F5C
0x180021097  xor     eax, eax
0x180021099  mov     [r11], ax
0x18002109d  jmp     loc_180020EBD
0x1800210a2  mov     eax, 80070216h
0x1800210a7  jmp     loc_180020FAF
```
