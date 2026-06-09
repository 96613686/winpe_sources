# GetDefaultExternalMosCacheDirectory

- ea: `0x18000771c`
- end: `0x1800078cb`
- name: `GetDefaultExternalMosCacheDirectory`
- size: `431`
- prototype: `__int64 __fastcall(PWSTR pszPathOut, size_t cchPathOut, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180007958`
- `0x180008c70`
- `0x180009be0`

## callees

- `0x180001c80`
- `0x180002802`
- `0x180006c44`
- `0x18000771c`
- `0x1800079d8`
- `0x18000cbb8`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800077b4`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800077b4`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800077d1`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800077ee`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800077d1`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x1800077ee`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007895`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007895`

## string_xrefs

- `0x1800077c8`: `GetExternalMosCacheDirectory`
- `0x1800077e5`: `GetDefaultExternalMosCacheDirectory`
- `0x18000788e`: `GetDefaultExternalMosCacheDirectory`

## pseudocode

```c
__int64 __fastcall GetDefaultExternalMosCacheDirectory(PWSTR pszPathOut, size_t cchPathOut, __int64 a3)
{
  __int64 v3; // rdi
  PWSTR v4; // rbx
  int MapsVolatileRegString; // eax
  HRESULT v6; // eax
  int v7; // eax
  unsigned int v8; // eax
  int v9; // r8d
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r8
  WCHAR v13; // ax
  unsigned int v14; // r9d
  PWSTR v15; // rcx
  unsigned int v16; // ebx
  unsigned int v17; // ecx
  __int128 v19; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v21; // [rsp+38h] [rbp-C8h]
  _BYTE v22[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPathIn[558]; // [rsp+44h] [rbp-BCh] BYREF

  v3 = (unsigned int)cchPathOut;
  v4 = pszPathOut;
  v19 = 0;
  v20 = 0;
  v21 = 7;
  LOWORD(v19) = 0;
  MapsVolatileRegString = RegUtils::GetMapsVolatileRegString(pszPathOut, cchPathOut, a3, &v19);
  if ( MapsVolatileRegString < 0 )
  {
    v9 = 182;
    goto LABEL_22;
  }
  if ( v20 )
  {
    v10 = (WCHAR *)&v19;
    if ( v21 > 7 )
      v10 = (WCHAR *)v19;
    v11 = v3;
    v12 = 2147483646;
    if ( (unsigned int)(v3 - 1) > 0x7FFFFFFE )
    {
      v14 = -2147024809;
      if ( (_DWORD)v3 )
        *v4 = 0;
    }
    else
    {
      do
      {
        if ( !v12 )
          break;
        v13 = *v10;
        if ( !*v10 )
          break;
        ++v10;
        *v4++ = v13;
        --v12;
        --v11;
      }
      while ( v11 );
      v14 = v11 == 0 ? 0x8007007A : 0;
      v15 = v4 - 1;
      if ( v11 )
        v15 = v4;
      *v15 = 0;
      if ( v11 )
        goto LABEL_17;
    }
    v9 = 194;
    v17 = v14;
LABEL_23:
    v8 = ZTraceReportPropagationNoThis(v17, "GetDefaultExternalMosCacheDirectory", v9);
    goto LABEL_24;
  }
  memset_0(v22, 0, 0x458u);
  MapsVolatileRegString = GetExternalStorageDeviceInfo(v22);
  if ( MapsVolatileRegString < 0 )
  {
    v9 = 189;
LABEL_22:
    v17 = MapsVolatileRegString;
    goto LABEL_23;
  }
  v6 = PathCchCombine(v4, (unsigned int)v3, pszPathIn, L"MapData\\");
  if ( v6 < 0 )
  {
    v7 = ZTraceReportOriginationNoThis(v6, "GetExternalMosCacheDirectory", 166);
    if ( v7 < 0 )
    {
      v8 = ZTraceReportOriginationNoThis(v7, "GetDefaultExternalMosCacheDirectory", 190);
LABEL_24:
      v16 = v8;
      goto LABEL_25;
    }
  }
LABEL_17:
  v16 = 0;
LABEL_25:
  std::wstring::~wstring(&v19);
  return v16;
}

```

## disassembly

```asm
0x18000771c  mov     [rsp-8+arg_10], rbx
0x180007721  push    rbp
0x180007722  push    rsi
0x180007723  push    rdi
0x180007724  lea     rbp, [rsp-3B0h]
0x18000772c  sub     rsp, 4B0h
0x180007733  mov     rax, cs:__security_cookie
0x18000773a  xor     rax, rsp
0x18000773d  mov     [rbp+3C0h+var_20], rax
0x180007744  mov     edi, edx
0x180007746  mov     rbx, rcx
0x180007749  xorps   xmm0, xmm0
0x18000774c  movups  [rsp+4C0h+var_4A0], xmm0
0x180007751  xor     esi, esi
0x180007753  mov     [rsp+4C0h+var_490], rsi
0x180007758  mov     [rsp+4C0h+var_488], 7
0x180007761  mov     word ptr [rsp+4C0h+var_4A0], si
0x180007766  lea     r9, [rsp+4C0h+var_4A0]
0x18000776b  call    ?GetMapsVolatileRegString@RegUtils@@SAJW4MapsRegKeys@@PEBG1PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegUtils::GetMapsVolatileRegString(MapsRegKeys,ushort const *,ushort const *,std::wstring *)
0x180007770  test    eax, eax
0x180007772  js      loc_180007886
0x180007778  cmp     [rsp+4C0h+var_490], rsi
0x18000777d  jnz     loc_180007804
0x180007783  xor     edx, edx; Val
0x180007785  mov     r8d, 458h; Size
0x18000778b  lea     rcx, [rsp+4C0h+var_480]; void *
0x180007790  call    memset_0
0x180007795  lea     rcx, [rsp+4C0h+var_480]
0x18000779a  call    GetExternalStorageDeviceInfo
0x18000779f  test    eax, eax
0x1800077a1  js      short loc_1800077F9
0x1800077a3  mov     edx, edi; cchPathOut
0x1800077a5  lea     r9, pszMore; "MapData\\"
0x1800077ac  lea     r8, [rsp+4C0h+pszPathIn]; pszPathIn
0x1800077b1  mov     rcx, rbx; pszPathOut
0x1800077b4  call    cs:__imp_PathCchCombine
0x1800077ba  test    eax, eax
0x1800077bc  jns     loc_18000786A
0x1800077c2  mov     r8d, 0A6h
0x1800077c8  lea     rdx, aGetexternalmos; "GetExternalMosCacheDirectory"
0x1800077cf  mov     ecx, eax
0x1800077d1  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800077d7  test    eax, eax
0x1800077d9  jns     loc_18000786A
0x1800077df  mov     r8d, 0BEh
0x1800077e5  lea     rdx, aGetdefaultexte; "GetDefaultExternalMosCacheDirectory"
0x1800077ec  mov     ecx, eax
0x1800077ee  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x1800077f4  jmp     loc_18000789B
0x1800077f9  mov     r8d, 0BDh
0x1800077ff  jmp     loc_18000788C
0x180007804  lea     rcx, [rsp+4C0h+var_4A0]
0x180007809  cmp     [rsp+4C0h+var_488], 7
0x18000780f  cmova   rcx, qword ptr [rsp+4C0h+var_4A0]
0x180007815  mov     rdx, rdi
0x180007818  lea     eax, [rdi-1]
0x18000781b  mov     r8d, 7FFFFFFEh
0x180007821  cmp     eax, r8d
0x180007824  ja      short loc_18000786E
0x180007826  test    r8, r8
0x180007829  jz      short loc_180007847
0x18000782b  movzx   eax, word ptr [rcx]
0x18000782e  test    ax, ax
0x180007831  jz      short loc_180007847
0x180007833  add     rcx, 2
0x180007837  mov     [rbx], ax
0x18000783a  add     rbx, 2
0x18000783e  dec     r8
0x180007841  sub     rdx, 1
0x180007845  jnz     short loc_180007826
0x180007847  mov     rax, rdx
0x18000784a  neg     rax
0x18000784d  sbb     r9d, r9d
0x180007850  not     r9d
0x180007853  and     r9d, 8007007Ah
0x18000785a  lea     rcx, [rbx-2]
0x18000785e  test    rdx, rdx
0x180007861  cmovnz  rcx, rbx
0x180007865  mov     [rcx], si
0x180007868  jz      short loc_18000787B
0x18000786a  mov     ebx, esi
0x18000786c  jmp     short loc_18000789D
0x18000786e  mov     r9d, 80070057h
0x180007874  test    edi, edi
0x180007876  jz      short loc_18000787B
0x180007878  mov     [rbx], si
0x18000787b  mov     r8d, 0C2h
0x180007881  mov     ecx, r9d
0x180007884  jmp     short loc_18000788E
0x180007886  mov     r8d, 0B6h
0x18000788c  mov     ecx, eax
0x18000788e  lea     rdx, aGetdefaultexte; "GetDefaultExternalMosCacheDirectory"
0x180007895  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000789b  mov     ebx, eax
0x18000789d  lea     rcx, [rsp+4C0h+var_4A0]
0x1800078a2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800078a7  mov     eax, ebx
0x1800078a9  mov     rcx, [rbp+3C0h+var_20]
0x1800078b0  xor     rcx, rsp; StackCookie
0x1800078b3  call    __security_check_cookie
0x1800078b8  mov     rbx, [rsp+4C0h+arg_10]
0x1800078c0  add     rsp, 4B0h
0x1800078c7  pop     rdi
0x1800078c8  pop     rsi
0x1800078c9  pop     rbp
0x1800078ca  retn
```
