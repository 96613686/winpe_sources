# MvGetConfiguration(ushort const *,uchar *,ulong *)

- ea: `0x18000ffb4`
- end: `0x1800100fa`
- name: `?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z`
- size: `326`
- prototype: `int __fastcall(const WCHAR *, PVOID pvData, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f998`

## callees

- `0x18000ff70`
- `0x18000ffb4`
- `0x180010100`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010007`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001005e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800100a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010007`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001005e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800100a1`

## string_xrefs

- `0x180010075`: `Software\Microsoft\Multivariant\InImageConfigurations`
- `0x1800100bf`: `onecoreuap\admin\prov\multivariant\common\src\mvregistryutils.cpp`

## pseudocode

```c
int __fastcall MvGetConfiguration(const WCHAR *a1, PVOID pvData, unsigned int *a3)
{
  unsigned int ValueW; // eax
  unsigned int v7; // r8d
  __int64 v8; // rdx
  wil::details::in1diag3 *v9; // rcx
  __int64 v10; // r9
  LSTATUS v12; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD pcbData; // [rsp+70h] [rbp+18h] BYREF

  pcbData = *a3;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, gc_wszRegMultivariant, a1, 2u, 0, pvData, &pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      v8 = 551;
LABEL_4:
      v9 = retaddr;
      v10 = ValueW;
      return wil::details::in1diag3::Return_Win32(v9, (void *)v8, v7, (const char *)v10, pdwType);
    }
    pcbData = *a3;
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Multivariant", a1, 2u, 0, pvData, &pcbData);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        v8 = 572;
        goto LABEL_4;
      }
      pcbData = *a3;
      v12 = RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Multivariant\\InImageConfigurations",
              a1,
              2u,
              0,
              pvData,
              &pcbData);
      v9 = retaddr;
      v10 = 2;
      if ( v12 )
      {
        v8 = 600;
        return wil::details::in1diag3::Return_Win32(v9, (void *)v8, v7, (const char *)v10, pdwType);
      }
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0x24E,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\mvregistryutils.cpp",
        (const char *)2,
        (unsigned int)"Missing reg value %ws is found in backup.",
        (const char *)a1);
    }
  }
  *a3 = pcbData;
  return 0;
}

```

## disassembly

```asm
0x18000ffb4  mov     r11, rsp
0x18000ffb7  mov     [r11+8], rbx
0x18000ffbb  mov     [r11+10h], rbp
0x18000ffbf  push    rsi
0x18000ffc0  push    rdi
0x18000ffc1  push    r15
0x18000ffc3  sub     rsp, 40h
0x18000ffc7  mov     eax, [r8]
0x18000ffca  mov     rbx, r8
0x18000ffcd  mov     [rsp+58h+arg_10], eax
0x18000ffd1  mov     rsi, rdx
0x18000ffd4  lea     rax, [r11+18h]
0x18000ffd8  mov     rdi, rcx
0x18000ffdb  mov     [r11-28h], rax
0x18000ffdf  mov     r8, rcx; lpValue
0x18000ffe2  mov     [r11-30h], rdx
0x18000ffe6  mov     ebp, 2
0x18000ffeb  mov     rdx, cs:?gc_wszRegMultivariant@@3PEBGEB; lpSubKey
0x18000fff2  mov     r15, 0FFFFFFFF80000002h
0x18000fff9  mov     r9d, ebp; dwFlags
0x18000fffc  mov     qword ptr [r11-38h], 0
0x180010004  mov     rcx, r15; hkey
0x180010007  call    cs:__imp_RegGetValueW
0x18001000d  test    eax, eax
0x18001000f  jz      loc_1800100D5
0x180010015  cmp     eax, ebp
0x180010017  jz      short loc_180010030
0x180010019  mov     edx, 227h; void *
0x18001001e  mov     rcx, [rsp+58h]; this
0x180010023  mov     r9d, eax; char *
0x180010026  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001002b  jmp     loc_1800100DD
0x180010030  mov     eax, [rbx]
0x180010032  lea     rdx, ?gc_wszRegMultivariantReadOnly@@3QBGB; "Software\\Microsoft\\Multivariant"
0x180010039  mov     [rsp+58h+arg_10], eax
0x18001003d  mov     r9d, ebp; dwFlags
0x180010040  lea     rax, [rsp+58h+arg_10]
0x180010045  mov     r8, rdi; lpValue
0x180010048  mov     [rsp+58h+pcbData], rax; pcbData
0x18001004d  mov     rcx, r15; hkey
0x180010050  mov     [rsp+58h+pvData], rsi; pvData
0x180010055  mov     [rsp+58h+pdwType], 0; pdwType
0x18001005e  call    cs:__imp_RegGetValueW
0x180010064  test    eax, eax
0x180010066  jz      short loc_1800100D5
0x180010068  cmp     eax, ebp
0x18001006a  jz      short loc_180010073
0x18001006c  mov     edx, 23Ch
0x180010071  jmp     short loc_18001001E
0x180010073  mov     eax, [rbx]
0x180010075  lea     rdx, ?gc_wszRegInImageConfigurations@@3QBGB; "Software\\Microsoft\\Multivariant\\InIm"...
0x18001007c  mov     [rsp+58h+arg_10], eax
0x180010080  mov     r9d, ebp; dwFlags
0x180010083  lea     rax, [rsp+58h+arg_10]
0x180010088  mov     r8, rdi; lpValue
0x18001008b  mov     [rsp+58h+pcbData], rax; pcbData
0x180010090  mov     rcx, r15; hkey
0x180010093  mov     [rsp+58h+pvData], rsi; pvData
0x180010098  mov     [rsp+58h+pdwType], 0; pdwType
0x1800100a1  call    cs:__imp_RegGetValueW
0x1800100a7  mov     rcx, [rsp+58h]; this
0x1800100ac  mov     r9d, ebp; char *
0x1800100af  test    eax, eax
0x1800100b1  jnz     short loc_1800100F0
0x1800100b3  lea     rax, aMissingRegValu; "Missing reg value %ws is found in backu"...
0x1800100ba  mov     [rsp+58h+pvData], rdi; char *
0x1800100bf  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800100c6  mov     [rsp+58h+pdwType], rax; unsigned int
0x1800100cb  mov     edx, 24Eh; void *
0x1800100d0  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800100d5  mov     eax, [rsp+58h+arg_10]
0x1800100d9  mov     [rbx], eax
0x1800100db  xor     eax, eax
0x1800100dd  mov     rbx, [rsp+58h+arg_0]
0x1800100e2  mov     rbp, [rsp+58h+arg_8]
0x1800100e7  add     rsp, 40h
0x1800100eb  pop     r15
0x1800100ed  pop     rdi
0x1800100ee  pop     rsi
0x1800100ef  retn
0x1800100f0  mov     edx, 258h
0x1800100f5  jmp     loc_180010026
```
