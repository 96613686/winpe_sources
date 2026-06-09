# HelperClass::GetTempFilePath(ushort const *,HSTRING__ * *)

- ea: `0x18001bc7c`
- end: `0x18001bdd9`
- name: `?GetTempFilePath@HelperClass@@SAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180016d70`

## callees

- `0x180003fc0`
- `0x180004b78`
- `0x180010c64`
- `0x180011390`
- `0x180011a20`
- `0x18001bc7c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bdaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001bdaa`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001bcda`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18001bcda`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001bd0a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001bd0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall HelperClass::GetTempFilePath(const unsigned __int16 *a1, HSTRING *a2)
{
  HSTRING v3; // rcx
  HRESULT v5; // ebx
  unsigned __int64 v6; // rcx
  HSTRING v7; // rax
  unsigned int v9; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  GUID pguid; // [rsp+40h] [rbp-C0h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v13[264]; // [rsp+A0h] [rbp-60h] BYREF

  *a2 = 0;
  v3 = 0;
  string = 0;
  pguid = 0;
  if ( a1 )
  {
    v5 = CoCreateGuid(&pguid);
    if ( v5 < 0 )
      goto LABEL_12;
    memset_0(sz, 0, 0x4Eu);
    v5 = StringFromGUID2(&pguid, sz, 39);
    if ( v5 < 0 )
      goto LABEL_12;
    memset_0(v13, 0, 0x208u);
    v5 = StringCchPrintfW(v13, 0x104u, L"%s\\%s.diagcab", a1, sz);
    if ( v5 < 0 )
      goto LABEL_12;
    v9 = 0;
    v6 = -1;
    do
      ++v6;
    while ( v13[v6] );
    v5 = ULongLongToUInt(v6, &v9);
    if ( v5 >= 0 )
      v5 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v13, v9);
    if ( v5 < 0 )
    {
LABEL_12:
      v3 = string;
    }
    else
    {
      v7 = string;
      v3 = 0;
      string = 0;
      *a2 = v7;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  WindowsDeleteString(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001bc7c  mov     [rsp-8+arg_10], rbx
0x18001bc81  mov     [rsp-8+arg_18], rsi
0x18001bc86  push    rbp
0x18001bc87  push    rdi
0x18001bc88  push    r14
0x18001bc8a  lea     rbp, [rsp-1C0h]
0x18001bc92  sub     rsp, 2C0h
0x18001bc99  mov     rax, cs:__security_cookie
0x18001bca0  xor     rax, rsp
0x18001bca3  mov     [rbp+1D0h+var_20], rax
0x18001bcaa  xor     r14d, r14d
0x18001bcad  mov     rsi, rcx
0x18001bcb0  mov     [rdx], r14
0x18001bcb3  mov     ecx, r14d
0x18001bcb6  mov     [rsp+2D0h+string], rcx
0x18001bcbb  xorps   xmm0, xmm0
0x18001bcbe  mov     rdi, rdx
0x18001bcc1  movups  xmmword ptr [rsp+2D0h+pguid.Data1], xmm0
0x18001bcc6  test    rsi, rsi
0x18001bcc9  jnz     short loc_18001BCD5
0x18001bccb  mov     ebx, 80070057h
0x18001bcd0  jmp     loc_18001BDAA
0x18001bcd5  lea     rcx, [rsp+2D0h+pguid]; pguid
0x18001bcda  call    cs:__imp_CoCreateGuid
0x18001bce0  mov     ebx, eax
0x18001bce2  test    eax, eax
0x18001bce4  js      loc_18001BDA5
0x18001bcea  xor     edx, edx; Val
0x18001bcec  lea     rcx, [rsp+2D0h+sz]; void *
0x18001bcf1  lea     r8d, [rdx+4Eh]; Size
0x18001bcf5  call    memset_0
0x18001bcfa  mov     r8d, 27h ; '''; cchMax
0x18001bd00  lea     rdx, [rsp+2D0h+sz]; lpsz
0x18001bd05  lea     rcx, [rsp+2D0h+pguid]; rguid
0x18001bd0a  call    cs:__imp_StringFromGUID2
0x18001bd10  mov     ebx, eax
0x18001bd12  test    eax, eax
0x18001bd14  js      loc_18001BDA5
0x18001bd1a  xor     edx, edx; Val
0x18001bd1c  lea     rcx, [rbp+1D0h+var_230]; void *
0x18001bd20  mov     r8d, 208h; Size
0x18001bd26  call    memset_0
0x18001bd2b  lea     rax, [rsp+2D0h+sz]
0x18001bd30  mov     r9, rsi
0x18001bd33  lea     r8, aSSDiagcab; "%s\\%s.diagcab"
0x18001bd3a  mov     [rsp+2D0h+var_2B0], rax
0x18001bd3f  mov     edx, 104h; unsigned __int64
0x18001bd44  lea     rcx, [rbp+1D0h+var_230]; unsigned __int16 *
0x18001bd48  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001bd4d  mov     ebx, eax
0x18001bd4f  test    eax, eax
0x18001bd51  js      short loc_18001BDA5
0x18001bd53  mov     [rsp+2D0h+var_2A0], r14d
0x18001bd58  lea     rax, [rbp+1D0h+var_230]
0x18001bd5c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001bd60  inc     rcx; unsigned __int64
0x18001bd63  cmp     [rax+rcx*2], r14w
0x18001bd68  jnz     short loc_18001BD60
0x18001bd6a  lea     rdx, [rsp+2D0h+var_2A0]; unsigned int *
0x18001bd6f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18001bd74  mov     ebx, eax
0x18001bd76  test    eax, eax
0x18001bd78  js      short loc_18001BD8F
0x18001bd7a  mov     r8d, [rsp+2D0h+var_2A0]; unsigned int
0x18001bd7f  lea     rdx, [rbp+1D0h+var_230]; unsigned __int16 *
0x18001bd83  lea     rcx, [rsp+2D0h+string]; this
0x18001bd88  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18001bd8d  mov     ebx, eax
0x18001bd8f  test    ebx, ebx
0x18001bd91  js      short loc_18001BDA5
0x18001bd93  mov     rax, [rsp+2D0h+string]
0x18001bd98  mov     rcx, r14
0x18001bd9b  mov     [rsp+2D0h+string], rcx
0x18001bda0  mov     [rdi], rax
0x18001bda3  jmp     short loc_18001BDAA
0x18001bda5  mov     rcx, [rsp+2D0h+string]; string
0x18001bdaa  call    cs:__imp_WindowsDeleteString
0x18001bdb0  mov     eax, ebx
0x18001bdb2  mov     rcx, [rbp+1D0h+var_20]
0x18001bdb9  xor     rcx, rsp; StackCookie
0x18001bdbc  call    __security_check_cookie
0x18001bdc1  lea     r11, [rsp+2D0h+var_10]
0x18001bdc9  mov     rbx, [r11+30h]
0x18001bdcd  mov     rsi, [r11+38h]
0x18001bdd1  mov     rsp, r11
0x18001bdd4  pop     r14
0x18001bdd6  pop     rdi
0x18001bdd7  pop     rbp
0x18001bdd8  retn
```
