# ParquetWriterConfig::ParquetWriterConfig(void *)

- ea: `0x18001ae70`
- end: `0x18001b09b`
- name: `??0ParquetWriterConfig@@QEAA@PEAX@Z`
- size: `555`
- prototype: `ParquetWriterConfig *__fastcall(ParquetWriterConfig *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800100c0`

## callees

- `0x18001ae70`
- `0x18030c190`
- `0x18030c3f0`
- `0x180358070`

## string_xrefs

- `0x18001af0f`: `ParquetWriterOutputterTotalColumnChunkBufferSizeInMB`
- `0x18001aeee`: `ParquetWriterOutputterMaxRowGroupSizeInMB`
- `0x18001af41`: `ParquetWriterOutputterMaxRowCountInRowGroup`
- `0x18001af74`: `ParquetWriterOutputterMaxLobSizeInMB`
- `0x18001afa3`: `ParquetWriterOutputterMaxRowCountInColumnChunkBuffer`
- `0x18001afd8`: `ParquetWriterOutputterDataPageSizeInMB`
- `0x18001b004`: `ParquetWriterOutputterDictionaryPageSizeLimitInMB`
- `0x18001b042`: `ParquetWriterOutputterEncodeTimeDateTime2ToInt96`

## pseudocode

```c
ParquetWriterConfig *__fastcall ParquetWriterConfig::ParquetWriterConfig(ParquetWriterConfig *this, void *a2)
{
  int v4; // eax
  int v5; // ecx
  int v6; // eax
  int v7; // ecx
  int v8; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // ebx
  int v12; // ecx
  int v13; // eax
  int v14; // ecx
  int v15; // eax
  int v16; // ecx
  int v17; // eax
  int v18; // edx
  unsigned __int64 v19; // rax
  int v21; // [rsp+20h] [rbp-18h] BYREF

  _CheckForDebuggerJustMyCode(word_1804EA142);
  if ( a2 )
  {
    v4 = (*(&g_configurationCallbacks + 1))(a2, L"ParquetWriterOutputterMaxRowGroupSizeInMB", &v21);
    v5 = 400;
    if ( v4 )
      v5 = v21;
    *(_QWORD *)this = (__int64)v5 << 20;
    v6 = (*(&g_configurationCallbacks + 1))(a2, L"ParquetWriterOutputterTotalColumnChunkBufferSizeInMB", &v21);
    v7 = 16;
    if ( v6 )
      v7 = v21;
    *((_QWORD *)this + 1) = (__int64)v7 << 20;
    v8 = (*(&g_configurationCallbacks + 1))(a2, L"ParquetWriterOutputterMaxRowCountInRowGroup", &v21);
    v9 = 0x200000;
    if ( v8 )
      v9 = v21;
    *((_QWORD *)this + 2) = v9;
    v10 = (*(&g_configurationCallbacks + 1))(a2, L"ParquetWriterOutputterMaxLobSizeInMB", &v21);
    v11 = 1;
    v12 = 1;
    if ( v10 )
      v12 = v21;
    *((_QWORD *)this + 3) = (__int64)v12 << 20;
    v13 = (*(&g_configurationCallbacks + 1))(a2, L"ParquetWriterOutputterMaxRowCountInColumnChunkBuffer", &v21);
    v14 = 900;
    if ( v13 )
      v14 = v21;
    *((_QWORD *)this + 4) = v14;
    v15 = (*(&g_configurationCallbacks + 1))(a2, L"ParquetWriterOutputterDataPageSizeInMB", &v21);
    v16 = 1;
    if ( v15 )
      v16 = v21;
    *((_QWORD *)this + 5) = (__int64)v16 << 20;
    v17 = (*(&g_configurationCallbacks + 1))(a2, L"ParquetWriterOutputterDictionaryPageSizeLimitInMB", &v21);
    v18 = 32;
    if ( v17 )
      v18 = v21;
    *((_QWORD *)this + 6) = (__int64)v18 << 20;
    if ( (unsigned int)g_configurationCallbacks(a2, L"ParquetWriterOutputterEncodeTimeDateTime2ToInt96", &v21) )
      v11 = v21;
    *((_BYTE *)this + 56) = v11 != 0;
    v19 = *((_QWORD *)this + 2);
    if ( *((_QWORD *)this + 4) > v19 )
      *((_QWORD *)this + 4) = v19;
  }
  else
  {
    *(_QWORD *)this = 419430400;
    *((_QWORD *)this + 2) = 0x200000;
    *((_QWORD *)this + 4) = 900;
    *((_QWORD *)this + 1) = 0x1000000;
    *((_QWORD *)this + 3) = 0x100000;
    *((_QWORD *)this + 5) = 0x100000;
    *((_QWORD *)this + 6) = 0x2000000;
    *((_BYTE *)this + 56) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x18001ae70  mov     [rsp+arg_18], rsi
0x18001ae75  push    rdi
0x18001ae76  sub     rsp, 30h
0x18001ae7a  mov     rax, cs:__security_cookie
0x18001ae81  xor     rax, rsp
0x18001ae84  mov     [rsp+38h+var_10], rax
0x18001ae89  mov     rdi, rcx
0x18001ae8c  mov     rsi, rdx
0x18001ae8f  lea     rcx, word_1804EA142
0x18001ae96  call    __CheckForDebuggerJustMyCode
0x18001ae9b  test    rsi, rsi
0x18001ae9e  jnz     short loc_18001AEE2
0x18001aea0  mov     ecx, 200000h
0x18001aea5  mov     qword ptr [rdi], 19000000h
0x18001aeac  mov     [rdi+10h], rcx
0x18001aeb0  mov     ecx, 384h
0x18001aeb5  mov     [rdi+20h], rcx
0x18001aeb9  mov     qword ptr [rdi+8], 1000000h
0x18001aec1  mov     qword ptr [rdi+18h], 100000h
0x18001aec9  mov     qword ptr [rdi+28h], 100000h
0x18001aed1  mov     qword ptr [rdi+30h], 2000000h
0x18001aed9  mov     byte ptr [rdi+38h], 1
0x18001aedd  jmp     loc_18001B080
0x18001aee2  mov     rax, qword ptr cs:?g_configurationCallbacks@@3UConfigurationCallbacks@@A+8; ConfigurationCallbacks g_configurationCallbacks
0x18001aee9  lea     r8, [rsp+38h+var_18]
0x18001aeee  lea     rdx, aParquetwritero_1; "ParquetWriterOutputterMaxRowGroupSizeIn"...
0x18001aef5  mov     [rsp+38h+arg_10], rbx
0x18001aefa  mov     rcx, rsi
0x18001aefd  call    cs:__guard_dispatch_icall_fptr
0x18001af03  mov     ecx, 190h
0x18001af08  lea     r8, [rsp+38h+var_18]
0x18001af0d  test    eax, eax
0x18001af0f  lea     rdx, aParquetwritero_6; "ParquetWriterOutputterTotalColumnChunkB"...
0x18001af16  cmovnz  ecx, [rsp+38h+var_18]
0x18001af1b  movsxd  rax, ecx
0x18001af1e  mov     rcx, rsi
0x18001af21  shl     rax, 14h
0x18001af25  mov     [rdi], rax
0x18001af28  mov     rax, qword ptr cs:?g_configurationCallbacks@@3UConfigurationCallbacks@@A+8; ConfigurationCallbacks g_configurationCallbacks
0x18001af2f  call    cs:__guard_dispatch_icall_fptr
0x18001af35  mov     ecx, 10h
0x18001af3a  lea     r8, [rsp+38h+var_18]
0x18001af3f  test    eax, eax
0x18001af41  lea     rdx, aParquetwritero_2; "ParquetWriterOutputterMaxRowCountInRowG"...
0x18001af48  cmovnz  ecx, [rsp+38h+var_18]
0x18001af4d  movsxd  rax, ecx
0x18001af50  mov     rcx, rsi
0x18001af53  shl     rax, 14h
0x18001af57  mov     [rdi+8], rax
0x18001af5b  mov     rax, qword ptr cs:?g_configurationCallbacks@@3UConfigurationCallbacks@@A+8; ConfigurationCallbacks g_configurationCallbacks
0x18001af62  call    cs:__guard_dispatch_icall_fptr
0x18001af68  mov     ecx, 200000h
0x18001af6d  lea     r8, [rsp+38h+var_18]
0x18001af72  test    eax, eax
0x18001af74  lea     rdx, aParquetwritero_4; "ParquetWriterOutputterMaxLobSizeInMB"
0x18001af7b  cmovnz  ecx, [rsp+38h+var_18]
0x18001af80  movsxd  rax, ecx
0x18001af83  mov     rcx, rsi
0x18001af86  mov     [rdi+10h], rax
0x18001af8a  mov     rax, qword ptr cs:?g_configurationCallbacks@@3UConfigurationCallbacks@@A+8; ConfigurationCallbacks g_configurationCallbacks
0x18001af91  call    cs:__guard_dispatch_icall_fptr
0x18001af97  mov     ebx, 1
0x18001af9c  lea     r8, [rsp+38h+var_18]
0x18001afa1  test    eax, eax
0x18001afa3  lea     rdx, aParquetwritero_3; "ParquetWriterOutputterMaxRowCountInColu"...
0x18001afaa  mov     ecx, ebx
0x18001afac  cmovnz  ecx, [rsp+38h+var_18]
0x18001afb1  movsxd  rax, ecx
0x18001afb4  mov     rcx, rsi
0x18001afb7  shl     rax, 14h
0x18001afbb  mov     [rdi+18h], rax
0x18001afbf  mov     rax, qword ptr cs:?g_configurationCallbacks@@3UConfigurationCallbacks@@A+8; ConfigurationCallbacks g_configurationCallbacks
0x18001afc6  call    cs:__guard_dispatch_icall_fptr
0x18001afcc  mov     ecx, 384h
0x18001afd1  lea     r8, [rsp+38h+var_18]
0x18001afd6  test    eax, eax
0x18001afd8  lea     rdx, aParquetwritero_0; "ParquetWriterOutputterDataPageSizeInMB"
0x18001afdf  cmovnz  ecx, [rsp+38h+var_18]
0x18001afe4  movsxd  rax, ecx
0x18001afe7  mov     rcx, rsi
0x18001afea  mov     [rdi+20h], rax
0x18001afee  mov     rax, qword ptr cs:?g_configurationCallbacks@@3UConfigurationCallbacks@@A+8; ConfigurationCallbacks g_configurationCallbacks
0x18001aff5  call    cs:__guard_dispatch_icall_fptr
0x18001affb  mov     ecx, ebx
0x18001affd  lea     r8, [rsp+38h+var_18]
0x18001b002  test    eax, eax
0x18001b004  lea     rdx, aParquetwritero_5; "ParquetWriterOutputterDictionaryPageSiz"...
0x18001b00b  cmovnz  ecx, [rsp+38h+var_18]
0x18001b010  movsxd  rax, ecx
0x18001b013  mov     rcx, rsi
0x18001b016  shl     rax, 14h
0x18001b01a  mov     [rdi+28h], rax
0x18001b01e  mov     rax, qword ptr cs:?g_configurationCallbacks@@3UConfigurationCallbacks@@A+8; ConfigurationCallbacks g_configurationCallbacks
0x18001b025  call    cs:__guard_dispatch_icall_fptr
0x18001b02b  mov     edx, 20h ; ' '
0x18001b030  lea     r8, [rsp+38h+var_18]
0x18001b035  test    eax, eax
0x18001b037  mov     rcx, rsi
0x18001b03a  cmovnz  edx, [rsp+38h+var_18]
0x18001b03f  movsxd  rax, edx
0x18001b042  lea     rdx, aParquetwritero_7; "ParquetWriterOutputterEncodeTimeDateTim"...
0x18001b049  shl     rax, 14h
0x18001b04d  mov     [rdi+30h], rax
0x18001b051  mov     rax, qword ptr cs:?g_configurationCallbacks@@3UConfigurationCallbacks@@A; ConfigurationCallbacks g_configurationCallbacks
0x18001b058  call    cs:__guard_dispatch_icall_fptr
0x18001b05e  test    eax, eax
0x18001b060  cmovnz  ebx, [rsp+38h+var_18]
0x18001b065  test    ebx, ebx
0x18001b067  mov     rbx, [rsp+38h+arg_10]
0x18001b06c  setnz   al
0x18001b06f  mov     [rdi+38h], al
0x18001b072  mov     rax, [rdi+10h]
0x18001b076  cmp     [rdi+20h], rax
0x18001b07a  jbe     short loc_18001B080
0x18001b07c  mov     [rdi+20h], rax
0x18001b080  mov     rax, rdi
0x18001b083  mov     rcx, [rsp+38h+var_10]
0x18001b088  xor     rcx, rsp; StackCookie
0x18001b08b  call    __security_check_cookie
0x18001b090  mov     rsi, [rsp+38h+arg_18]
0x18001b095  add     rsp, 30h
0x18001b099  pop     rdi
0x18001b09a  retn
```
