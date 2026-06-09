# SystemSettings::Prov::CProvisioningDisplayStringSetting::get_Description(HSTRING__ * *)

- ea: `0x180021020`
- end: `0x1800210e9`
- name: `?get_Description@CProvisioningDisplayStringSetting@Prov@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `201`
- prototype: `int(SystemSettings::Prov::CProvisioningDisplayStringSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800087ec`
- `0x18001cbe4`
- `0x18001e560`
- `0x180021020`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800210ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800210ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800210ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800210ca`

## pseudocode

```c
__int64 __fastcall SystemSettings::Prov::CProvisioningDisplayStringSetting::get_Description(
        SystemSettings::Prov::CProvisioningDisplayStringSetting *this,
        HSTRING *a2)
{
  __int64 v3; // r9
  unsigned __int64 v4; // rcx
  int v5; // ebx
  const unsigned __int16 *v6; // r9
  unsigned int v7; // r8d
  const unsigned __int16 *v8; // rdx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v12; // [rsp+30h] [rbp+8h] BYREF
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *((_QWORD *)this + 26);
  string = 0;
  if ( v3 )
  {
    v12 = 0;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(v3 + 2 * v4) );
    v5 = ULongLongToUInt(v4, &v12);
    if ( v5 < 0 )
      goto LABEL_8;
    v7 = v12;
    v8 = v6;
  }
  else
  {
    v7 = 0;
    v8 = &word_1800330E8;
  }
  v5 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v8, v7);
  if ( v5 < 0 )
  {
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      (const char *)(unsigned int)v5,
      v10);
    WindowsDeleteString(string);
    return (unsigned int)v5;
  }
  *a2 = string;
  string = 0;
  WindowsDeleteString(0);
  return 0;
}

```

## disassembly

```asm
0x180021020  mov     rax, rsp
0x180021023  mov     [rax+18h], rbx
0x180021027  mov     [rax+20h], rsi
0x18002102b  push    rdi; int
0x18002102c  sub     rsp, 20h
0x180021030  xor     esi, esi
0x180021032  mov     rdi, rdx
0x180021035  mov     [rdx], rsi
0x180021038  mov     r9, [rcx+0D0h]
0x18002103f  mov     [rax+10h], rsi
0x180021043  test    r9, r9
0x180021046  jz      short loc_180021073
0x180021048  mov     [rax+8], esi
0x18002104b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002104f  inc     rcx; unsigned __int64
0x180021052  cmp     [r9+rcx*2], si
0x180021057  jnz     short loc_18002104F
0x180021059  lea     rdx, [rsp+28h+arg_0]; unsigned int *
0x18002105e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180021063  mov     ebx, eax
0x180021065  test    eax, eax
0x180021067  js      short loc_18002108D
0x180021069  mov     r8d, [rsp+28h+arg_0]
0x18002106e  mov     rdx, r9
0x180021071  jmp     short loc_18002107D
0x180021073  xor     r8d, r8d; unsigned int
0x180021076  lea     rdx, word_1800330E8; unsigned __int16 *
0x18002107d  lea     rcx, [rsp+28h+string]; this
0x180021082  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180021087  mov     ebx, eax
0x180021089  test    eax, eax
0x18002108b  jns     short loc_1800210BB
0x18002108d  mov     rcx, [rsp+28h]; this
0x180021092  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180021099  mov     r9d, ebx; char *
0x18002109c  mov     edx, 0E1h; void *
0x1800210a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800210a6  mov     rcx, [rsp+28h+string]; string
0x1800210ab  call    cs:__imp_WindowsDeleteString
0x1800210b2  nop     dword ptr [rax+rax+00h]
0x1800210b7  mov     eax, ebx
0x1800210b9  jmp     short loc_1800210D8
0x1800210bb  mov     rax, [rsp+28h+string]
0x1800210c0  xor     ecx, ecx; string
0x1800210c2  mov     [rdi], rax
0x1800210c5  mov     [rsp+28h+string], rsi
0x1800210ca  call    cs:__imp_WindowsDeleteString
0x1800210d1  nop     dword ptr [rax+rax+00h]
0x1800210d6  xor     eax, eax
0x1800210d8  mov     rbx, [rsp+28h+arg_10]
0x1800210dd  mov     rsi, [rsp+28h+arg_18]
0x1800210e2  add     rsp, 20h
0x1800210e6  pop     rdi
0x1800210e7  retn
```
