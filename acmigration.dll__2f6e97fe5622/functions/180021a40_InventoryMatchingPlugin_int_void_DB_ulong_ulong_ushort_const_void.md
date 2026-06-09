# InventoryMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x180021a40`
- end: `0x180021c93`
- name: `?InventoryMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `595`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x18000b720`
- `0x180020d1c`
- `0x180021a40`
- `0x18003f0b0`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180021bb8`
- `KERNEL32!LocalFree` at `0x180021bb8`
- `ntdll!RtlFreeHeap` at `0x180021be0`
- `ntdll!RtlFreeHeap` at `0x180021be0`

## string_xrefs

- `0x180021ad1`: `Enter InventoryMatchingPlugin.`
- `0x180021ade`: `InventoryMatchingPlugin`
- `0x180021c38`: `InventoryMatchingPlugin`
- `0x180021c2b`: `InventoryMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall InventoryMatchingPlugin(
        int *a1,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        void *a7)
{
  unsigned int v7; // r9d
  __int128 *v8; // rdx
  const char *v10; // rax
  int *v11; // [rsp+30h] [rbp-118h] BYREF
  int v12; // [rsp+38h] [rbp-110h] BYREF
  int v13; // [rsp+3Ch] [rbp-10Ch] BYREF
  int v14; // [rsp+40h] [rbp-108h] BYREF
  int v15; // [rsp+44h] [rbp-104h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-100h] BYREF
  PVOID P; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v18; // [rsp+58h] [rbp-F0h] BYREF
  LPCWSTR *v19[14]; // [rsp+60h] [rbp-E8h] BYREF
  const std::exception *v20; // [rsp+D0h] [rbp-78h] BYREF
  __int128 v21; // [rsp+D8h] [rbp-70h] BYREF
  __m128i si128; // [rsp+E8h] [rbp-60h]
  __m128i v23[2]; // [rsp+F8h] [rbp-50h] BYREF
  __m128i v24[2]; // [rsp+118h] [rbp-30h] BYREF

  v19[13] = (LPCWSTR *)-2LL;
  v11 = a1;
  hMem = 0;
  v12 = 0;
  v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v21) = 0;
  v24[0] = 0;
  v24[1] = si128;
  v24[0].m128i_i16[0] = 0;
  v23[0] = 0;
  v23[1] = si128;
  v23[0].m128i_i16[0] = 0;
  v18 = 0;
  P = 0;
  v15 = -2147467259;
  v13 = 0;
  v14 = 0;
  AslLogCallPrintf(3, "InventoryMatchingPlugin", 357, "Enter InventoryMatchingPlugin.");
  *v11 = 0;
  v19[0] = &a6;
  v19[1] = (LPCWSTR *)&v21;
  v19[2] = (LPCWSTR *)&v11;
  v19[3] = (LPCWSTR *)&a5;
  v19[4] = (LPCWSTR *)&hMem;
  v19[5] = (LPCWSTR *)&v12;
  v19[6] = (LPCWSTR *)v24;
  v19[7] = (LPCWSTR *)&v13;
  v19[8] = (LPCWSTR *)&v14;
  v19[9] = (LPCWSTR *)v23;
  v19[10] = (LPCWSTR *)&v18;
  v19[11] = (LPCWSTR *)&P;
  v19[12] = (LPCWSTR *)&v15;
  lambda_f8c8c34b84b8557185e1f0d0c38e6c1b_::operator()(v19);
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( P )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    P = 0;
  }
  try
  {
    v8 = &v21;
    if ( si128.m128i_i64[1] > 7uLL )
      LODWORD(v8) = v21;
    AppCompatUtility::AddCacheMatchingPlugin(
      (AppCompatUtility *)(unsigned int)*v11,
      (int)v8,
      (const unsigned __int16 *)(unsigned int)a5,
      v7);
  }
  catch ( const std::exception *v20 )
  {
    v10 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v20 + 8LL))(v20);
    AslLogCallPrintf(1, "InventoryMatchingPlugin", 550, "Exception: %s", v10);
  }
  catch ( ... )
  {
    AslLogCallPrintf(1, "InventoryMatchingPlugin", 554, "Unhandled exception.");
  }
  AslLogCallPrintf(3, "InventoryMatchingPlugin", 557, "InventoryMatchingPlugin Matched = %d", *v11);
  std::wstring::~wstring(v23);
  std::wstring::~wstring(v24);
  std::wstring::~wstring(&v21);
  return 1;
}

```

## disassembly

```asm
0x180021a40  mov     r11, rsp
0x180021a43  sub     rsp, 148h
0x180021a4a  mov     qword ptr [r11-80h], 0FFFFFFFFFFFFFFFEh
0x180021a52  mov     rax, cs:__security_cookie
0x180021a59  xor     rax, rsp
0x180021a5c  mov     [rsp+148h+var_10], rax
0x180021a64  mov     [rsp+148h+var_118], rcx
0x180021a69  mov     [rsp+148h+hMem], 0
0x180021a72  mov     [rsp+148h+var_110], 0
0x180021a7a  xorps   xmm0, xmm0
0x180021a7d  movups  xmmword ptr [r11-70h], xmm0
0x180021a82  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180021a8a  movdqu  xmmword ptr [r11-60h], xmm1
0x180021a90  xor     eax, eax
0x180021a92  mov     [r11-70h], ax
0x180021a97  movups  xmmword ptr [r11-30h], xmm0
0x180021a9c  movdqu  xmmword ptr [r11-20h], xmm1
0x180021aa2  mov     [r11-30h], ax
0x180021aa7  movups  xmmword ptr [r11-50h], xmm0
0x180021aac  movdqu  xmmword ptr [r11-40h], xmm1
0x180021ab2  mov     [r11-50h], ax
0x180021ab7  mov     [rsp+148h+var_F0], rax
0x180021abc  mov     [rsp+148h+P], rax
0x180021ac1  mov     [rsp+148h+var_104], 80004005h
0x180021ac9  mov     [rsp+148h+var_10C], eax
0x180021acd  mov     [rsp+148h+var_108], eax
0x180021ad1  lea     r9, aEnterInventory; "Enter InventoryMatchingPlugin."
0x180021ad8  mov     r8d, 165h
0x180021ade  lea     rdx, aInventorymatch; "InventoryMatchingPlugin"
0x180021ae5  lea     ecx, [rax+3]
0x180021ae8  call    AslLogCallPrintf
0x180021aed  mov     rax, [rsp+148h+var_118]
0x180021af2  mov     dword ptr [rax], 0
0x180021af8  lea     rax, [rsp+148h+arg_28]
0x180021b00  mov     [rsp+148h+var_E8], rax
0x180021b05  lea     rax, [rsp+148h+var_70]
0x180021b0d  mov     [rsp+148h+var_E0], rax
0x180021b12  lea     rax, [rsp+148h+var_118]
0x180021b17  mov     [rsp+148h+var_D8], rax
0x180021b1c  lea     rax, [rsp+148h+arg_20]
0x180021b24  mov     [rsp+148h+var_D0], rax
0x180021b29  lea     rax, [rsp+148h+hMem]
0x180021b2e  mov     [rsp+148h+var_C8], rax
0x180021b36  lea     rax, [rsp+148h+var_110]
0x180021b3b  mov     [rsp+148h+var_C0], rax
0x180021b43  lea     rax, [rsp+148h+var_30]
0x180021b4b  mov     [rsp+148h+var_B8], rax
0x180021b53  lea     rax, [rsp+148h+var_10C]
0x180021b58  mov     [rsp+148h+var_B0], rax
0x180021b60  lea     rax, [rsp+148h+var_108]
0x180021b65  mov     [rsp+148h+var_A8], rax
0x180021b6d  lea     rax, [rsp+148h+var_50]
0x180021b75  mov     [rsp+148h+var_A0], rax
0x180021b7d  lea     rax, [rsp+148h+var_F0]
0x180021b82  mov     [rsp+148h+var_98], rax
0x180021b8a  lea     rax, [rsp+148h+P]
0x180021b8f  mov     [rsp+148h+var_90], rax
0x180021b97  lea     rax, [rsp+148h+var_104]
0x180021b9c  mov     [rsp+148h+var_88], rax
0x180021ba4  lea     rcx, [rsp+148h+var_E8]
0x180021ba9  call    _lambda_f8c8c34b84b8557185e1f0d0c38e6c1b___operator__
0x180021bae  mov     rcx, [rsp+148h+hMem]; hMem
0x180021bb3  test    rcx, rcx
0x180021bb6  jz      short loc_180021BC7
0x180021bb8  call    cs:__imp_LocalFree
0x180021bbe  mov     [rsp+148h+hMem], 0
0x180021bc7  mov     r8, [rsp+148h+P]; P
0x180021bcc  test    r8, r8
0x180021bcf  jz      short loc_180021BEF
0x180021bd1  mov     rcx, gs:60h
0x180021bda  xor     edx, edx; Flags
0x180021bdc  mov     rcx, [rcx+30h]; HeapHandle
0x180021be0  call    cs:__imp_RtlFreeHeap
0x180021be6  mov     [rsp+148h+P], 0
0x180021bef  lea     rdx, [rsp+148h+var_70]
0x180021bf7  cmp     [rsp+148h+var_58], 7
0x180021c00  cmova   rdx, qword ptr [rsp+148h+var_70]; int
0x180021c09  mov     r8d, dword ptr [rsp+148h+arg_20]; unsigned __int16 *
0x180021c11  mov     rcx, [rsp+148h+var_118]
0x180021c16  mov     ecx, [rcx]; this
0x180021c18  call    ?AddCacheMatchingPlugin@AppCompatUtility@@YAXHPEBGK@Z; AppCompatUtility::AddCacheMatchingPlugin(int,ushort const *,ulong)
0x180021c1d  nop
0x180021c1e  mov     rax, [rsp+148h+var_118]
0x180021c23  mov     r8d, [rax]
0x180021c26  mov     [rsp+148h+var_128], r8d
0x180021c2b  lea     r9, aInventorymatch_0; "InventoryMatchingPlugin Matched = %d"
0x180021c32  mov     r8d, 22Dh
0x180021c38  lea     rdx, aInventorymatch; "InventoryMatchingPlugin"
0x180021c3f  mov     ecx, 3
0x180021c44  call    AslLogCallPrintf
0x180021c49  nop
0x180021c4a  lea     rcx, [rsp+148h+var_50]; void *
0x180021c52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021c57  nop
0x180021c58  lea     rcx, [rsp+148h+var_30]; void *
0x180021c60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021c65  nop
0x180021c66  lea     rcx, [rsp+148h+var_70]; void *
0x180021c6e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021c73  mov     eax, 1
0x180021c78  mov     rcx, [rsp+148h+var_10]
0x180021c80  xor     rcx, rsp; StackCookie
0x180021c83  call    __security_check_cookie
0x180021c88  add     rsp, 148h
0x180021c8f  retn
0x180021c90  jmp     short loc_180021C1E
```
