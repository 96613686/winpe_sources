# AiInitializeLib

- ea: `0x180004154`
- end: `0x180004234`
- name: `AiInitializeLib`
- size: `224`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800028d0`

## callees

- `0x180004000`
- `0x180004154`
- `0x1800086b0`
- `0x18000957a`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800041af`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800041af`

## string_xrefs

- `0x1800041c2`: `\Registry\Machine\System\CurrentControlSet\Control\AppID\Configuration`

## pseudocode

```c
__int64 AiInitializeLib()
{
  __int64 v0; // rbx
  __int64 v1; // rdx
  __int64 v2; // rcx
  NTSTATUS v3; // edi
  __int64 v4; // r8
  __int64 v5; // rcx
  _QWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v8[2]; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v9[3]; // [rsp+40h] [rbp-18h] BYREF
  int v10; // [rsp+80h] [rbp+28h] BYREF

  memset_0(AiPerfStats, 0, sizeof(AiPerfStats));
  v0 = 0;
  AipAlgInitialized = 1;
  AipAlgHandle = 0;
  while ( 1 )
  {
    v3 = BCryptOpenAlgorithmProvider(&AipAlgHandle + v0, (&off_18000B0D8)[v0], L"Microsoft Primitive Provider", 0);
    if ( v3 < 0 )
      break;
    v0 = (unsigned int)(v0 + 1);
    if ( (_DWORD)v0 )
    {
      v7[0] = 9306252;
      v7[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\AppID\\Configuration";
      v8[0] = 1966108;
      v8[1] = L"UsePublisherId";
      v9[0] = 2883626;
      v3 = 0;
      v9[1] = L"UseSystemIdentityOnly";
      v10 = 0;
      ((void (__fastcall *)(__int64, _QWORD *, _QWORD *, int *))AiRegReadDwordValue)(v2, v7, v8, &v10);
      ((void (__fastcall *)(__int64, _QWORD *, _QWORD *, int *))AiRegReadDwordValue)(v5, v7, v9, &v10);
      return (unsigned int)v3;
    }
  }
  AiFreeLib(v2, v1, v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180004154  push    rbp
0x180004156  push    rbx
0x180004157  push    rsi
0x180004158  push    rdi
0x180004159  mov     rbp, rsp
0x18000415c  sub     rsp, 58h
0x180004160  xor     edx, edx; Val
0x180004162  lea     rcx, AiPerfStats; void *
0x180004169  mov     r8d, 0C0h; Size
0x18000416f  call    memset_0
0x180004174  xor     ebx, ebx
0x180004176  mov     cs:AipAlgInitialized, 1
0x180004180  mov     cs:AipAlgHandle, 0
0x18000418b  lea     rsi, __ImageBase
0x180004192  mov     rdx, ds:rva off_18000B0D8[rsi+rbx*8]; pszAlgId
0x18000419a  lea     rcx, rva AipAlgHandle[rsi]
0x1800041a1  lea     rcx, [rcx+rbx*8]; phAlgorithm
0x1800041a5  xor     r9d, r9d; dwFlags
0x1800041a8  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800041af  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800041b5  mov     edi, eax
0x1800041b7  test    eax, eax
0x1800041b9  js      short loc_180004224
0x1800041bb  inc     ebx
0x1800041bd  cmp     ebx, 1
0x1800041c0  jb      short loc_180004192
0x1800041c2  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800041c9  mov     [rbp+var_38], 8E008Ch
0x1800041d1  mov     [rbp+var_30], rax
0x1800041d5  lea     r9, [rbp+arg_0]
0x1800041d9  lea     rax, aUsepublisherid; "UsePublisherId"
0x1800041e0  mov     [rbp+var_28], 1E001Ch
0x1800041e8  mov     [rbp+var_20], rax
0x1800041ec  lea     r8, [rbp+var_28]
0x1800041f0  lea     rax, aUsesystemident; "UseSystemIdentityOnly"
0x1800041f7  mov     [rbp+var_18], 2C002Ah
0x1800041ff  xor     edi, edi
0x180004201  mov     [rbp+var_10], rax
0x180004205  lea     rdx, [rbp+var_38]
0x180004209  mov     [rbp+arg_0], edi
0x18000420c  call    AiRegReadDwordValue
0x180004211  lea     r9, [rbp+arg_0]
0x180004215  lea     r8, [rbp+var_18]
0x180004219  lea     rdx, [rbp+var_38]
0x18000421d  call    AiRegReadDwordValue
0x180004222  jmp     short loc_180004229
0x180004224  call    AiFreeLib
0x180004229  mov     eax, edi
0x18000422b  add     rsp, 58h
0x18000422f  pop     rdi
0x180004230  pop     rsi
0x180004231  pop     rbx
0x180004232  pop     rbp
0x180004233  retn
```
