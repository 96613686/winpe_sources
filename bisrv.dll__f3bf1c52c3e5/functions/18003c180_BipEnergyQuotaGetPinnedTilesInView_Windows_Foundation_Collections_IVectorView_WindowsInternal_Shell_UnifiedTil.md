# BipEnergyQuotaGetPinnedTilesInView(Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::UnifiedTile::Shim::UnifiedTileIdentifier *> *,_RTL_DYNAMIC_HASH_TABLE *)

- ea: `0x18003c180`
- end: `0x18003c3ea`
- name: `?BipEnergyQuotaGetPinnedTilesInView@@YAJPEAU?$IVectorView@PEAVUnifiedTileIdentifier@Shim@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@PEAU_RTL_DYNAMIC_HASH_TABLE@@@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180064f90`

## callees

- `0x18001ef7c`
- `0x18003c180`
- `0x18003c3f0`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x18003c308`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18003c308`
- `ntdll!RtlInsertEntryHashTable` at `0x18003c369`
- `ntdll!RtlInsertEntryHashTable` at `0x18003c369`
- `ntdll!RtlFreeHeap` at `0x18003c3e2`
- `ntdll!RtlFreeHeap` at `0x18003c3e2`
- `ntdll!RtlAllocateHeap` at `0x18003c331`
- `ntdll!RtlAllocateHeap` at `0x18003c331`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c274`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c3a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c274`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c3a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c2b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003c2b2`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18003c2d2`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18003c2d2`

## pseudocode

```c
__int64 __fastcall BipEnergyQuotaGetPinnedTilesInView(__int64 a1, __int64 a2)
{
  unsigned int v2; // r14d
  int v4; // eax
  int v5; // r12d
  unsigned int i; // esi
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  __int64 v10; // rbx
  __int64 v11; // r15
  WCHAR *v12; // rdi
  WCHAR v13; // ax
  _OWORD *Heap; // rax
  void *v15; // rbx
  unsigned int v16; // ebx
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+34h] [rbp-CCh] BYREF
  int v20; // [rsp+38h] [rbp-C8h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+3Ch] [rbp-C4h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v23; // [rsp+48h] [rbp-B8h] BYREF
  int v24; // [rsp+50h] [rbp-B0h] BYREF
  int *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  __int128 v28; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h]
  WCHAR packageFamilyName[72]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR packageRelativeApplicationId[72]; // [rsp+120h] [rbp+20h] BYREF

  v2 = 0;
  v23 = a1;
  packageRelativeApplicationIdLength = 0;
  v29 = 0;
  v18 = 0;
  v25 = &v18;
  v28 = 0;
  v20 = 0;
  string = 0;
  packageFamilyNameLength = 0;
  v26 = 0;
  v27 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 56LL))(a1, &v24);
  *v25 = v4;
  wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::UnifiedTile::Shim::UnifiedTileIdentifier *>>::get_at_current(
    &v23,
    0);
  v5 = v24;
  for ( i = 0;
        ;
        wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::UnifiedTile::Shim::UnifiedTileIdentifier *>>::get_at_current(
          &v23,
          i) )
  {
    if ( i == v5 || *v25 < 0 )
    {
      v15 = 0;
      goto LABEL_16;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v27 + 48LL))(v27, &v20);
    if ( v18 >= 0 && v20 == 1 )
    {
      v7 = v27;
      v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 64LL);
      WindowsDeleteString(string);
      string = 0;
      v18 = v8(v7, &string);
      if ( v18 >= 0 )
      {
        packageFamilyNameLength = 65;
        packageRelativeApplicationIdLength = 66;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( !ParseApplicationUserModelId(
                StringRawBuffer,
                &packageFamilyNameLength,
                packageFamilyName,
                &packageRelativeApplicationIdLength,
                packageRelativeApplicationId) )
        {
          v10 = -1;
          do
            ++v10;
          while ( packageFamilyName[v10] );
          v11 = qword_1800C4148;
          v12 = packageFamilyName;
          packageFamilyNameLength = v10;
          if ( (_DWORD)v10 )
          {
            do
            {
              v13 = RtlUpcaseUnicodeChar(*v12++);
              v11 = v13 + 39 * v11;
              ++v2;
            }
            while ( v2 < (unsigned int)v10 );
          }
          Heap = RtlAllocateHeap(BipHeap, 0, 0x18u);
          v2 = 0;
          v15 = Heap;
          if ( !Heap )
            break;
          *Heap = 0;
          *((_QWORD *)Heap + 2) = 0;
          v29 = 0;
          v28 = 0;
          if ( !(unsigned __int8)RtlInsertEntryHashTable(a2, Heap, v11, &v28) )
            break;
        }
      }
    }
    ++i;
  }
  v18 = -2147024882;
LABEL_16:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
  if ( v15 )
    RtlFreeHeap(BipHeap, 0, v15);
  v16 = v18;
  WindowsDeleteString(string);
  return v16;
}

```

## disassembly

```asm
0x18003c180  push    rbp
0x18003c182  push    rbx
0x18003c183  push    rsi
0x18003c184  push    rdi
0x18003c185  push    r12
0x18003c187  push    r13
0x18003c189  push    r14
0x18003c18b  push    r15
0x18003c18d  lea     rbp, [rsp-0C8h]
0x18003c195  sub     rsp, 1C8h
0x18003c19c  mov     rax, cs:__security_cookie
0x18003c1a3  xor     rax, rsp
0x18003c1a6  mov     [rbp+100h+var_50], rax
0x18003c1ad  xor     r14d, r14d
0x18003c1b0  mov     [rsp+200h+var_1B8], rcx
0x18003c1b5  xor     eax, eax
0x18003c1b7  mov     [rsp+200h+packageRelativeApplicationIdLength], r14d
0x18003c1bc  mov     [rbp+100h+var_180], rax
0x18003c1c0  xorps   xmm0, xmm0
0x18003c1c3  lea     rax, [rsp+200h+var_1D0]
0x18003c1c8  mov     [rsp+200h+var_1D0], r14d
0x18003c1cd  mov     [rsp+200h+var_1A8], rax
0x18003c1d2  mov     r13, rdx
0x18003c1d5  movups  [rsp+200h+var_190], xmm0
0x18003c1da  mov     [rsp+200h+var_1C8], r14d
0x18003c1df  lea     rdx, [rsp+200h+var_1B0]
0x18003c1e4  mov     [rsp+200h+string], r14
0x18003c1e9  mov     [rsp+200h+packageFamilyNameLength], r14d
0x18003c1ee  mov     [rsp+200h+var_1A0], r14d
0x18003c1f3  mov     [rsp+200h+var_198], r14
0x18003c1f8  mov     rax, [rcx]
0x18003c1fb  mov     rax, [rax+38h]
0x18003c1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c204  mov     rcx, [rsp+200h+var_1A8]
0x18003c209  xor     edx, edx
0x18003c20b  mov     [rcx], eax
0x18003c20d  lea     rcx, [rsp+200h+var_1B8]
0x18003c212  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVUnifiedTileIdentifier@Shim@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::UnifiedTile::Shim::UnifiedTileIdentifier *>>::get_at_current(uint)
0x18003c217  mov     r12d, [rsp+200h+var_1B0]
0x18003c21c  mov     esi, r14d
0x18003c21f  mov     rax, [rsp+200h+var_1A8]
0x18003c224  cmp     esi, r12d
0x18003c227  jz      loc_18003C386
0x18003c22d  cmp     [rax], r14d
0x18003c230  jl      loc_18003C386
0x18003c236  mov     rcx, [rsp+200h+var_198]
0x18003c23b  lea     rdx, [rsp+200h+var_1C8]
0x18003c240  mov     rax, [rcx]
0x18003c243  mov     rax, [rax+30h]
0x18003c247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c24c  mov     [rsp+200h+var_1D0], eax
0x18003c250  test    eax, eax
0x18003c252  js      loc_18003C373
0x18003c258  cmp     [rsp+200h+var_1C8], 1
0x18003c25d  jnz     loc_18003C373
0x18003c263  mov     rdi, [rsp+200h+var_198]
0x18003c268  mov     rcx, [rsp+200h+string]; string
0x18003c26d  mov     rax, [rdi]
0x18003c270  mov     rbx, [rax+40h]
0x18003c274  call    cs:__imp_WindowsDeleteString
0x18003c27a  lea     rdx, [rsp+200h+string]
0x18003c27f  mov     [rsp+200h+string], r14
0x18003c284  mov     rcx, rdi
0x18003c287  mov     rax, rbx
0x18003c28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c28f  mov     [rsp+200h+var_1D0], eax
0x18003c293  test    eax, eax
0x18003c295  js      loc_18003C373
0x18003c29b  mov     rcx, [rsp+200h+string]; string
0x18003c2a0  xor     edx, edx; length
0x18003c2a2  mov     [rsp+200h+packageFamilyNameLength], 41h ; 'A'
0x18003c2aa  mov     [rsp+200h+packageRelativeApplicationIdLength], 42h ; 'B'
0x18003c2b2  call    cs:__imp_WindowsGetStringRawBuffer
0x18003c2b8  lea     rcx, [rbp+100h+var_E0]
0x18003c2bc  mov     [rsp+200h+packageRelativeApplicationId], rcx; packageRelativeApplicationId
0x18003c2c1  lea     r9, [rsp+200h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18003c2c6  mov     rcx, rax; applicationUserModelId
0x18003c2c9  lea     r8, [rbp+100h+packageFamilyName]; packageFamilyName
0x18003c2cd  lea     rdx, [rsp+200h+packageFamilyNameLength]; packageFamilyNameLength
0x18003c2d2  call    cs:__imp_ParseApplicationUserModelId
0x18003c2d8  test    eax, eax
0x18003c2da  jnz     loc_18003C373
0x18003c2e0  lea     rax, [rbp+100h+packageFamilyName]
0x18003c2e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003c2e8  inc     rbx
0x18003c2eb  cmp     [rax+rbx*2], r14w
0x18003c2f0  jnz     short loc_18003C2E8
0x18003c2f2  mov     r15, cs:qword_1800C4148
0x18003c2f9  lea     rdi, [rbp+100h+packageFamilyName]
0x18003c2fd  mov     [rsp+200h+packageFamilyNameLength], ebx
0x18003c301  test    ebx, ebx
0x18003c303  jz      short loc_18003C324
0x18003c305  movzx   ecx, word ptr [rdi]; Source
0x18003c308  call    cs:__imp_RtlUpcaseUnicodeChar
0x18003c30e  imul    r15, 27h ; '''
0x18003c312  movzx   ecx, ax
0x18003c315  lea     rdi, [rdi+2]
0x18003c319  add     r15, rcx
0x18003c31c  inc     r14d
0x18003c31f  cmp     r14d, ebx
0x18003c322  jb      short loc_18003C305
0x18003c324  mov     rcx, cs:BipHeap; HeapHandle
0x18003c32b  xor     edx, edx; Flags
0x18003c32d  lea     r8d, [rdx+18h]; Size
0x18003c331  call    cs:__imp_RtlAllocateHeap
0x18003c337  xor     r14d, r14d
0x18003c33a  mov     rbx, rax
0x18003c33d  test    rax, rax
0x18003c340  jz      loc_18003C3CC
0x18003c346  xorps   xmm0, xmm0
0x18003c349  lea     r9, [rsp+200h+var_190]
0x18003c34e  movups  xmmword ptr [rbx], xmm0
0x18003c351  xor     eax, eax
0x18003c353  mov     r8, r15
0x18003c356  mov     [rbx+10h], rax
0x18003c35a  mov     rdx, rbx
0x18003c35d  mov     rcx, r13
0x18003c360  mov     [rbp+100h+var_180], rax
0x18003c364  movups  [rsp+200h+var_190], xmm0
0x18003c369  call    cs:__imp_RtlInsertEntryHashTable
0x18003c36f  test    al, al
0x18003c371  jz      short loc_18003C3CC
0x18003c373  inc     esi
0x18003c375  lea     rcx, [rsp+200h+var_1B8]
0x18003c37a  mov     edx, esi
0x18003c37c  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@PEAVUnifiedTileIdentifier@Shim@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::UnifiedTile::Shim::UnifiedTileIdentifier *>>::get_at_current(uint)
0x18003c381  jmp     loc_18003C21F
0x18003c386  mov     rbx, r14
0x18003c389  lea     rcx, [rsp+200h+var_198]
0x18003c38e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003c393  test    rbx, rbx
0x18003c396  jnz     short loc_18003C3D6
0x18003c398  mov     rcx, [rsp+200h+string]; string
0x18003c39d  mov     ebx, [rsp+200h+var_1D0]
0x18003c3a1  call    cs:__imp_WindowsDeleteString
0x18003c3a7  mov     eax, ebx
0x18003c3a9  mov     rcx, [rbp+100h+var_50]
0x18003c3b0  xor     rcx, rsp; StackCookie
0x18003c3b3  call    __security_check_cookie
0x18003c3b8  add     rsp, 1C8h
0x18003c3bf  pop     r15
0x18003c3c1  pop     r14
0x18003c3c3  pop     r13
0x18003c3c5  pop     r12
0x18003c3c7  pop     rdi
0x18003c3c8  pop     rsi
0x18003c3c9  pop     rbx
0x18003c3ca  pop     rbp
0x18003c3cb  retn
0x18003c3cc  mov     [rsp+200h+var_1D0], 8007000Eh
0x18003c3d4  jmp     short loc_18003C389
0x18003c3d6  mov     rcx, cs:BipHeap; HeapHandle
0x18003c3dd  mov     r8, rbx; P
0x18003c3e0  xor     edx, edx; Flags
0x18003c3e2  call    cs:__imp_RtlFreeHeap
0x18003c3e8  jmp     short loc_18003C398
```
