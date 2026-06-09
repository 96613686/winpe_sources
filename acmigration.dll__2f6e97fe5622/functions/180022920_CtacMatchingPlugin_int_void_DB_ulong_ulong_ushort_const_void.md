# CtacMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x180022920`
- end: `0x180022af2`
- name: `?CtacMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `466`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x18000b720`
- `0x180022148`
- `0x180022920`
- `0x18003f0b0`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180022a33`
- `KERNEL32!LocalFree` at `0x180022a33`
- `ntdll!RtlFreeHeap` at `0x180022a5b`
- `ntdll!RtlFreeHeap` at `0x180022a5b`

## string_xrefs

- `0x180022989`: `Enter CtacMatchingPlugin.`
- `0x180022996`: `CtacMatchingPlugin`
- `0x180022ab3`: `CtacMatchingPlugin`
- `0x180022aa6`: `CtacMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CtacMatchingPlugin(
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
  int *v11; // [rsp+30h] [rbp-B8h] BYREF
  int v12; // [rsp+38h] [rbp-B0h] BYREF
  int v13; // [rsp+3Ch] [rbp-ACh] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-A8h] BYREF
  PVOID P; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v16; // [rsp+50h] [rbp-98h] BYREF
  LPCWSTR *v17[10]; // [rsp+58h] [rbp-90h] BYREF
  const std::exception *v18; // [rsp+A8h] [rbp-40h] BYREF
  __int128 v19; // [rsp+B0h] [rbp-38h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-28h]

  v17[9] = (LPCWSTR *)-2LL;
  v11 = a1;
  hMem = 0;
  v12 = 0;
  v19 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19) = 0;
  v13 = -2147467259;
  v16 = 0;
  P = 0;
  AslLogCallPrintf(3, "CtacMatchingPlugin", 208, "Enter CtacMatchingPlugin.");
  *v11 = 0;
  v17[0] = &a6;
  v17[1] = (LPCWSTR *)&v19;
  v17[2] = (LPCWSTR *)&v11;
  v17[3] = (LPCWSTR *)&a5;
  v17[4] = (LPCWSTR *)&hMem;
  v17[5] = (LPCWSTR *)&v12;
  v17[6] = (LPCWSTR *)&v16;
  v17[7] = (LPCWSTR *)&P;
  v17[8] = (LPCWSTR *)&v13;
  lambda_22f33554c469371d3a24008c516f0d10_::operator()(v17);
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
    v8 = &v19;
    if ( si128.m128i_i64[1] > 7uLL )
      LODWORD(v8) = v19;
    AppCompatUtility::AddCacheMatchingPlugin(
      (AppCompatUtility *)(unsigned int)*v11,
      (int)v8,
      (const unsigned __int16 *)(unsigned int)a5,
      v7);
  }
  catch ( const std::exception *v18 )
  {
    v10 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v18 + 8LL))(v18);
    AslLogCallPrintf(1, "CtacMatchingPlugin", 349, "Exception: %s", v10);
  }
  catch ( ... )
  {
    AslLogCallPrintf(1, "CtacMatchingPlugin", 353, "Unhandled exception.");
  }
  AslLogCallPrintf(3, "CtacMatchingPlugin", 356, "CtacMatchingPlugin Matched = %d", *v11);
  std::wstring::~wstring(&v19);
  return 1;
}

```

## disassembly

```asm
0x180022920  mov     r11, rsp
0x180022923  sub     rsp, 0E8h
0x18002292a  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x180022932  mov     rax, cs:__security_cookie
0x180022939  xor     rax, rsp
0x18002293c  mov     [rsp+0E8h+var_18], rax
0x180022944  mov     [rsp+0E8h+var_B8], rcx
0x180022949  mov     [rsp+0E8h+hMem], 0
0x180022952  mov     [rsp+0E8h+var_B0], 0
0x18002295a  xorps   xmm0, xmm0
0x18002295d  movups  xmmword ptr [r11-38h], xmm0
0x180022962  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18002296a  movdqu  xmmword ptr [r11-28h], xmm1
0x180022970  xor     eax, eax
0x180022972  mov     [r11-38h], ax
0x180022977  mov     [rsp+0E8h+var_AC], 80004005h
0x18002297f  mov     [rsp+0E8h+var_98], rax
0x180022984  mov     [rsp+0E8h+P], rax
0x180022989  lea     r9, aEnterCtacmatch; "Enter CtacMatchingPlugin."
0x180022990  mov     r8d, 0D0h
0x180022996  lea     rdx, aCtacmatchingpl_0; "CtacMatchingPlugin"
0x18002299d  lea     ecx, [rax+3]
0x1800229a0  call    AslLogCallPrintf
0x1800229a5  mov     rax, [rsp+0E8h+var_B8]
0x1800229aa  mov     dword ptr [rax], 0
0x1800229b0  lea     rax, [rsp+0E8h+arg_28]
0x1800229b8  mov     [rsp+0E8h+var_90], rax
0x1800229bd  lea     rax, [rsp+0E8h+var_38]
0x1800229c5  mov     [rsp+0E8h+var_88], rax
0x1800229ca  lea     rax, [rsp+0E8h+var_B8]
0x1800229cf  mov     [rsp+0E8h+var_80], rax
0x1800229d4  lea     rax, [rsp+0E8h+arg_20]
0x1800229dc  mov     [rsp+0E8h+var_78], rax
0x1800229e1  lea     rax, [rsp+0E8h+hMem]
0x1800229e6  mov     [rsp+0E8h+var_70], rax
0x1800229eb  lea     rax, [rsp+0E8h+var_B0]
0x1800229f0  mov     [rsp+0E8h+var_68], rax
0x1800229f8  lea     rax, [rsp+0E8h+var_98]
0x1800229fd  mov     [rsp+0E8h+var_60], rax
0x180022a05  lea     rax, [rsp+0E8h+P]
0x180022a0a  mov     [rsp+0E8h+var_58], rax
0x180022a12  lea     rax, [rsp+0E8h+var_AC]
0x180022a17  mov     [rsp+0E8h+var_50], rax
0x180022a1f  lea     rcx, [rsp+0E8h+var_90]
0x180022a24  call    _lambda_22f33554c469371d3a24008c516f0d10___operator__
0x180022a29  mov     rcx, [rsp+0E8h+hMem]; hMem
0x180022a2e  test    rcx, rcx
0x180022a31  jz      short loc_180022A42
0x180022a33  call    cs:__imp_LocalFree
0x180022a39  mov     [rsp+0E8h+hMem], 0
0x180022a42  mov     r8, [rsp+0E8h+P]; P
0x180022a47  test    r8, r8
0x180022a4a  jz      short loc_180022A6A
0x180022a4c  mov     rcx, gs:60h
0x180022a55  xor     edx, edx; Flags
0x180022a57  mov     rcx, [rcx+30h]; HeapHandle
0x180022a5b  call    cs:__imp_RtlFreeHeap
0x180022a61  mov     [rsp+0E8h+P], 0
0x180022a6a  lea     rdx, [rsp+0E8h+var_38]
0x180022a72  cmp     [rsp+0E8h+var_20], 7
0x180022a7b  cmova   rdx, qword ptr [rsp+0E8h+var_38]; int
0x180022a84  mov     r8d, dword ptr [rsp+0E8h+arg_20]; unsigned __int16 *
0x180022a8c  mov     rcx, [rsp+0E8h+var_B8]
0x180022a91  mov     ecx, [rcx]; this
0x180022a93  call    ?AddCacheMatchingPlugin@AppCompatUtility@@YAXHPEBGK@Z; AppCompatUtility::AddCacheMatchingPlugin(int,ushort const *,ulong)
0x180022a98  nop
0x180022a99  mov     rax, [rsp+0E8h+var_B8]
0x180022a9e  mov     r8d, [rax]
0x180022aa1  mov     [rsp+0E8h+var_C8], r8d
0x180022aa6  lea     r9, aCtacmatchingpl_1; "CtacMatchingPlugin Matched = %d"
0x180022aad  mov     r8d, 164h
0x180022ab3  lea     rdx, aCtacmatchingpl_0; "CtacMatchingPlugin"
0x180022aba  mov     ecx, 3
0x180022abf  call    AslLogCallPrintf
0x180022ac4  nop
0x180022ac5  lea     rcx, [rsp+0E8h+var_38]; void *
0x180022acd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022ad2  mov     eax, 1
0x180022ad7  mov     rcx, [rsp+0E8h+var_18]
0x180022adf  xor     rcx, rsp; StackCookie
0x180022ae2  call    __security_check_cookie
0x180022ae7  add     rsp, 0E8h
0x180022aee  retn
0x180022aef  jmp     short loc_180022A99
```
