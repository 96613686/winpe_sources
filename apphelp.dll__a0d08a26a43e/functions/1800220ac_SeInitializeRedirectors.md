# SeInitializeRedirectors

- ea: `0x1800220ac`
- end: `0x18002242f`
- name: `SeInitializeRedirectors`
- size: `899`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800213ec`

## callees

- `0x18000f114`
- `0x1800220ac`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!LdrLoadDll` at `0x180022281`
- `ntdll!LdrLoadDll` at `0x180022281`
- `ntdll!RtlInitUnicodeStringEx` at `0x180022263`
- `ntdll!RtlInitUnicodeStringEx` at `0x180022263`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800222b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800222b9`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800222cb`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800222cb`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800222e5`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800222e5`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18002229f`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18002229f`

## string_xrefs

- `0x1800221f4`: `apphelp.dll`
- `0x18002218f`: `\system32\`
- `0x180022399`: `Failed to StringCchCatW system32`
- `0x1800223b0`: `Failed to StringCchCopyW`

## pseudocode

```c
__int64 SeInitializeRedirectors()
{
  WCHAR *v0; // rax
  __int64 v1; // r11
  _DWORD *v2; // rdi
  unsigned __int64 v3; // rsi
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  WCHAR *v7; // rdx
  __int64 v8; // rdx
  WCHAR *v9; // rax
  __int64 v10; // r9
  const wchar_t *v11; // r10
  __int64 v12; // rcx
  WCHAR *v13; // rax
  __int64 v14; // rdx
  WCHAR *v15; // rcx
  __int64 v16; // rdx
  WCHAR *v17; // rax
  __int64 v18; // r9
  const wchar_t *v19; // rcx
  WCHAR *v20; // rax
  __int64 v21; // r8
  WCHAR *v22; // rcx
  NTSTATUS inited; // ebx
  HRSRC ResourceW; // rax
  HRSRC v25; // rbx
  HGLOBAL Resource; // rax
  const char *v27; // r9
  __int64 v28; // r8
  __int64 result; // rax
  PVOID BaseAddress; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SourceString[264]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(SourceString, 0, 0x208u);
  v0 = SourceString;
  BaseAddress = 0;
  v1 = 2147483646;
  DestinationString = 0;
  v2 = 0;
  v3 = 0;
  v4 = 2147483646;
  v5 = 2147352624;
  v6 = 260;
  do
  {
    if ( !v4 )
      break;
    if ( !*(_WORD *)v5 )
      break;
    *v0 = *(_WORD *)v5;
    v5 += 2;
    ++v0;
    --v4;
    --v6;
  }
  while ( v6 );
  v7 = v0 - 1;
  if ( v6 )
    v7 = v0;
  *v7 = 0;
  if ( !v6 )
  {
    v27 = "Failed to StringCchCopyW";
    v28 = 114;
    goto LABEL_46;
  }
  v8 = 260;
  v9 = SourceString;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v10 = (260 - v8) & -(__int64)(v8 != 0);
  if ( !v8 )
    goto LABEL_45;
  v11 = L"\\system32\\";
  v12 = 2147483646;
  v13 = &SourceString[v10];
  v14 = 260 - v10;
  if ( v10 != 260 )
  {
    do
    {
      if ( !v12 )
        break;
      if ( !*v11 )
        break;
      *v13++ = *v11++;
      --v12;
      --v14;
    }
    while ( v14 );
  }
  v15 = v13 - 1;
  if ( v14 )
    v15 = v13;
  *v15 = 0;
  if ( !v14 )
  {
LABEL_45:
    v27 = "Failed to StringCchCatW system32";
    v28 = 122;
LABEL_46:
    inited = -1073741789;
    goto LABEL_38;
  }
  v16 = 260;
  v17 = SourceString;
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  v18 = (260 - v16) & -(__int64)(v16 != 0);
  if ( !v16 )
    goto LABEL_42;
  v19 = L"apphelp.dll";
  v20 = &SourceString[v18];
  v21 = 260 - v18;
  if ( 260 != v18 )
  {
    do
    {
      if ( !v1 )
        break;
      if ( !*v19 )
        break;
      *v20++ = *v19++;
      --v1;
      --v21;
    }
    while ( v21 );
  }
  v22 = v20 - 1;
  if ( v21 )
    v22 = v20;
  *v22 = 0;
  if ( !v21 )
  {
LABEL_42:
    inited = -1073741789;
    AslLogCallPrintf(1, "SeInitializeRedirectors", 130, "Failed to StringCchCatW %S", L"apphelp.dll");
    goto LABEL_39;
  }
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited < 0 )
  {
    AslLogCallPrintf(1, "SeInitializeRedirectors", 140, "Failed to init unicode string");
    goto LABEL_39;
  }
  inited = LdrLoadDll(0, 0, &DestinationString, &BaseAddress);
  if ( inited < 0 )
  {
    AslLogCallPrintf(1, "SeInitializeRedirectors", 147, "Failed to load %S", DestinationString.Buffer);
    goto LABEL_39;
  }
  ResourceW = FindResourceW((HMODULE)BaseAddress, (LPCWSTR)0x64, (LPCWSTR)0xA);
  v25 = ResourceW;
  if ( !ResourceW )
  {
    inited = -1073741685;
    AslLogCallPrintf(1, "SeInitializeRedirectors", 161, "Failed to find redirector table");
    goto LABEL_39;
  }
  Resource = LoadResource((HMODULE)BaseAddress, ResourceW);
  if ( !Resource )
  {
    inited = -1073741687;
    AslLogCallPrintf(1, "SeInitializeRedirectors", 168, "Failed to load redirector table");
    goto LABEL_39;
  }
  v2 = LockResource(Resource);
  if ( !v2 )
  {
    inited = -1073741801;
    AslLogCallPrintf(1, "SeInitializeRedirectors", 175, "Failed to lock redirector table");
    goto LABEL_39;
  }
  v3 = SizeofResource((HMODULE)BaseAddress, v25);
  if ( v3 < 0x18 )
  {
    inited = -1073741761;
    AslLogCallPrintf(1, "SeInitializeRedirectors", 182, "Corrupt redirector table");
    goto LABEL_39;
  }
  if ( *v2 == 1919247465 && v2[1] == 1 )
  {
    inited = 0;
    goto LABEL_39;
  }
  inited = -1073741761;
  v27 = "Corrupt redirector table";
  v28 = 189;
LABEL_38:
  AslLogCallPrintf(1, "SeInitializeRedirectors", v28, v27);
LABEL_39:
  qword_180081040 = (__int64)v2;
  result = (unsigned int)inited;
  qword_180081048 = v3;
  return result;
}

```

## disassembly

```asm
0x1800220ac  push    rbp
0x1800220ae  push    rbx
0x1800220af  push    rsi
0x1800220b0  push    rdi
0x1800220b1  push    r14
0x1800220b3  push    r15
0x1800220b5  lea     rbp, [rsp-178h]
0x1800220bd  sub     rsp, 278h
0x1800220c4  mov     rax, cs:__security_cookie
0x1800220cb  xor     rax, rsp
0x1800220ce  mov     [rbp+1A0h+var_40], rax
0x1800220d5  xor     edx, edx; Val
0x1800220d7  lea     rcx, [rsp+2A0h+SourceString]; void *
0x1800220dc  mov     r8d, 208h; Size
0x1800220e2  call    memset_0
0x1800220e7  xor     r14d, r14d
0x1800220ea  lea     rax, [rsp+2A0h+SourceString]
0x1800220ef  xorps   xmm0, xmm0
0x1800220f2  mov     [rsp+2A0h+BaseAddress], r14
0x1800220f7  mov     r11d, 7FFFFFFEh
0x1800220fd  mov     r8d, 104h
0x180022103  movups  xmmword ptr [rsp+2A0h+DestinationString.Length], xmm0
0x180022108  lea     r15d, [r14+1]
0x18002210c  mov     edi, r14d
0x18002210f  mov     esi, r14d
0x180022112  mov     ecx, r11d
0x180022115  mov     edx, 7FFE0030h
0x18002211a  mov     r9d, r8d
0x18002211d  test    rcx, rcx
0x180022120  jz      short loc_180022140
0x180022122  movzx   r10d, word ptr [rdx]
0x180022126  test    r10w, r10w
0x18002212a  jz      short loc_180022140
0x18002212c  mov     [rax], r10w
0x180022130  add     rdx, 2
0x180022134  add     rax, 2
0x180022138  sub     rcx, r15
0x18002213b  sub     r9, r15
0x18002213e  jnz     short loc_18002211D
0x180022140  test    r9, r9
0x180022143  lea     rdx, [rax-2]
0x180022147  cmovnz  rdx, rax
0x18002214b  mov     [rdx], r14w
0x18002214f  jz      loc_1800223B0
0x180022155  mov     rdx, r8
0x180022158  lea     rax, [rsp+2A0h+SourceString]
0x18002215d  cmp     [rax], r14w
0x180022161  jz      short loc_18002216C
0x180022163  add     rax, 2
0x180022167  sub     rdx, r15
0x18002216a  jnz     short loc_18002215D
0x18002216c  mov     rcx, r8
0x18002216f  mov     rax, rdx
0x180022172  sub     rcx, rdx
0x180022175  neg     rax
0x180022178  sbb     r9, r9
0x18002217b  and     r9, rcx
0x18002217e  test    rdx, rdx
0x180022181  jz      loc_180022399
0x180022187  mov     rdx, r8
0x18002218a  lea     rax, [rsp+2A0h+SourceString]
0x18002218f  lea     r10, aSystem32_0; "\\system32\\"
0x180022196  mov     rcx, r11
0x180022199  lea     rax, [rax+r9*2]
0x18002219d  sub     rdx, r9
0x1800221a0  jz      short loc_1800221C5
0x1800221a2  test    rcx, rcx
0x1800221a5  jz      short loc_1800221C5
0x1800221a7  movzx   r9d, word ptr [r10]
0x1800221ab  test    r9w, r9w
0x1800221af  jz      short loc_1800221C5
0x1800221b1  mov     [rax], r9w
0x1800221b5  add     r10, 2
0x1800221b9  add     rax, 2
0x1800221bd  sub     rcx, r15
0x1800221c0  sub     rdx, r15
0x1800221c3  jnz     short loc_1800221A2
0x1800221c5  test    rdx, rdx
0x1800221c8  lea     rcx, [rax-2]
0x1800221cc  cmovnz  rcx, rax
0x1800221d0  mov     [rcx], r14w
0x1800221d4  jz      loc_180022399
0x1800221da  mov     rdx, r8
0x1800221dd  lea     rax, [rsp+2A0h+SourceString]
0x1800221e2  cmp     [rax], r14w
0x1800221e6  jz      short loc_1800221F1
0x1800221e8  add     rax, 2
0x1800221ec  sub     rdx, r15
0x1800221ef  jnz     short loc_1800221E2
0x1800221f1  mov     rcx, r8
0x1800221f4  lea     r10, aApphelpDll_1; "apphelp.dll"
0x1800221fb  sub     rcx, rdx
0x1800221fe  mov     rax, rdx
0x180022201  neg     rax
0x180022204  sbb     r9, r9
0x180022207  and     r9, rcx
0x18002220a  test    rdx, rdx
0x18002220d  jz      loc_18002235A
0x180022213  lea     rax, [rsp+2A0h+SourceString]
0x180022218  mov     rcx, r10
0x18002221b  lea     rax, [rax+r9*2]
0x18002221f  sub     r8, r9
0x180022222  jz      short loc_180022244
0x180022224  test    r11, r11
0x180022227  jz      short loc_180022244
0x180022229  movzx   edx, word ptr [rcx]
0x18002222c  test    dx, dx
0x18002222f  jz      short loc_180022244
0x180022231  mov     [rax], dx
0x180022234  add     rcx, 2
0x180022238  add     rax, 2
0x18002223c  sub     r11, r15
0x18002223f  sub     r8, r15
0x180022242  jnz     short loc_180022224
0x180022244  test    r8, r8
0x180022247  lea     rcx, [rax-2]
0x18002224b  cmovnz  rcx, rax
0x18002224f  mov     [rcx], r14w
0x180022253  jz      loc_18002235A
0x180022259  lea     rdx, [rsp+2A0h+SourceString]; SourceString
0x18002225e  lea     rcx, [rsp+2A0h+DestinationString]; DestinationString
0x180022263  call    cs:__imp_RtlInitUnicodeStringEx
0x180022269  mov     ebx, eax
0x18002226b  test    eax, eax
0x18002226d  js      loc_1800223BF
0x180022273  lea     r9, [rsp+2A0h+BaseAddress]; BaseAddress
0x180022278  xor     edx, edx; LoadFlags
0x18002227a  lea     r8, [rsp+2A0h+DestinationString]; Name
0x18002227f  xor     ecx, ecx; SearchPath
0x180022281  call    cs:__imp_LdrLoadDll
0x180022287  mov     ebx, eax
0x180022289  test    eax, eax
0x18002228b  js      loc_1800223D1
0x180022291  mov     rcx, [rsp+2A0h+BaseAddress]; hModule
0x180022296  mov     edx, 64h ; 'd'; lpName
0x18002229b  lea     r8d, [rdx-5Ah]; lpType
0x18002229f  call    cs:__imp_FindResourceW
0x1800222a5  mov     rbx, rax
0x1800222a8  test    rax, rax
0x1800222ab  jz      loc_180022382
0x1800222b1  mov     rcx, [rsp+2A0h+BaseAddress]; hModule
0x1800222b6  mov     rdx, rax; hResInfo
0x1800222b9  call    cs:__imp_LoadResource
0x1800222bf  test    rax, rax
0x1800222c2  jz      loc_1800223EA
0x1800222c8  mov     rcx, rax; hResData
0x1800222cb  call    cs:__imp_LockResource
0x1800222d1  mov     rdi, rax
0x1800222d4  test    rax, rax
0x1800222d7  jz      loc_180022401
0x1800222dd  mov     rcx, [rsp+2A0h+BaseAddress]; hModule
0x1800222e2  mov     rdx, rbx; hResInfo
0x1800222e5  call    cs:__imp_SizeofResource
0x1800222eb  mov     esi, eax
0x1800222ed  cmp     rsi, 18h
0x1800222f1  jb      loc_180022418
0x1800222f7  cmp     dword ptr [rdi], 72656469h
0x1800222fd  jz      short loc_18002234F
0x1800222ff  mov     ebx, 0C000003Fh
0x180022304  lea     r9, aCorruptRedirec; "Corrupt redirector table"
0x18002230b  mov     r8d, 0BDh
0x180022311  lea     rdx, aSeinitializere; "SeInitializeRedirectors"
0x180022318  mov     ecx, r15d
0x18002231b  call    AslLogCallPrintf
0x180022320  mov     cs:qword_180081040, rdi
0x180022327  mov     eax, ebx
0x180022329  mov     cs:qword_180081048, rsi
0x180022330  mov     rcx, [rbp+1A0h+var_40]
0x180022337  xor     rcx, rsp; StackCookie
0x18002233a  call    __security_check_cookie
0x18002233f  add     rsp, 278h
0x180022346  pop     r15
0x180022348  pop     r14
0x18002234a  pop     rdi
0x18002234b  pop     rsi
0x18002234c  pop     rbx
0x18002234d  pop     rbp
0x18002234e  retn
0x18002234f  cmp     [rdi+4], r15d
0x180022353  jnz     short loc_1800222FF
0x180022355  mov     ebx, r14d
0x180022358  jmp     short loc_180022320
0x18002235a  mov     ebx, 0C0000023h
0x18002235f  mov     [rsp+2A0h+var_280], r10
0x180022364  lea     r9, aFailedToString_2; "Failed to StringCchCatW %S"
0x18002236b  mov     r8d, 82h
0x180022371  lea     rdx, aSeinitializere; "SeInitializeRedirectors"
0x180022378  mov     ecx, r15d
0x18002237b  call    AslLogCallPrintf
0x180022380  jmp     short loc_180022320
0x180022382  mov     ebx, 0C000008Bh
0x180022387  lea     r9, aFailedToFindRe; "Failed to find redirector table"
0x18002238e  mov     r8d, 0A1h
0x180022394  jmp     loc_180022311
0x180022399  lea     r9, aFailedToString_1; "Failed to StringCchCatW system32"
0x1800223a0  mov     r8d, 7Ah ; 'z'
0x1800223a6  mov     ebx, 0C0000023h
0x1800223ab  jmp     loc_180022311
0x1800223b0  lea     r9, aFailedToString_0; "Failed to StringCchCopyW"
0x1800223b7  mov     r8d, 72h ; 'r'
0x1800223bd  jmp     short loc_1800223A6
0x1800223bf  lea     r9, aFailedToInitUn; "Failed to init unicode string"
0x1800223c6  mov     r8d, 8Ch
0x1800223cc  jmp     loc_180022311
0x1800223d1  mov     rax, [rsp+2A0h+DestinationString.Buffer]
0x1800223d6  lea     r9, aFailedToLoadS; "Failed to load %S"
0x1800223dd  mov     [rsp+2A0h+var_280], rax
0x1800223e2  mov     r8d, 93h
0x1800223e8  jmp     short loc_180022371
0x1800223ea  mov     ebx, 0C0000089h
0x1800223ef  lea     r9, aFailedToLoadRe; "Failed to load redirector table"
0x1800223f6  mov     r8d, 0A8h
0x1800223fc  jmp     loc_180022311
0x180022401  mov     ebx, 0C0000017h
0x180022406  lea     r9, aFailedToLockRe; "Failed to lock redirector table"
0x18002240d  mov     r8d, 0AFh
0x180022413  jmp     loc_180022311
0x180022418  mov     ebx, 0C000003Fh
0x18002241d  lea     r9, aCorruptRedirec; "Corrupt redirector table"
0x180022424  mov     r8d, 0B6h
0x18002242a  jmp     loc_180022311
```
