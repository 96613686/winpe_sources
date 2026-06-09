# QueryAttributes

- ea: `0x1800b1e8c`
- end: `0x1800b2067`
- name: `QueryAttributes`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b2070`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x1800b1d1c`
- `0x1800b1d40`
- `0x1800b1e8c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800b1ee7`
- `ntdll!RtlInitUnicodeString` at `0x1800b1f1e`
- `ntdll!RtlInitUnicodeString` at `0x1800b1f4d`
- `ntdll!RtlInitUnicodeString` at `0x1800b1f79`
- `ntdll!RtlInitUnicodeString` at `0x1800b1fa8`
- `ntdll!RtlInitUnicodeString` at `0x1800b1ee7`
- `ntdll!RtlInitUnicodeString` at `0x1800b1f1e`
- `ntdll!RtlInitUnicodeString` at `0x1800b1f4d`
- `ntdll!RtlInitUnicodeString` at `0x1800b1f79`
- `ntdll!RtlInitUnicodeString` at `0x1800b1fa8`
- `ntdll!NtQuerySecurityAttributesToken` at `0x1800b1fee`
- `ntdll!NtQuerySecurityAttributesToken` at `0x1800b1fee`

## pseudocode

```c
__int64 __fastcall QueryAttributes(_QWORD *a1, char a2, __int64 *a3)
{
  __int64 v6; // rbp
  unsigned int v7; // ebx
  unsigned int v8; // edi
  int SecurityAttributesToken; // eax
  unsigned int v10; // esi
  unsigned int v12[4]; // [rsp+30h] [rbp-88h] BYREF
  _UNICODE_STRING DestinationString[4]; // [rsp+40h] [rbp-78h] BYREF

  memset_0(DestinationString, 0, sizeof(DestinationString));
  v6 = 0;
  v12[0] = 0;
  *a3 = 0;
  if ( (a2 & 1) != 0 )
  {
    v7 = 100;
    RtlInitUnicodeString(DestinationString, L"EDP://PolicyFlags");
    v8 = 1;
  }
  else
  {
    v8 = 0;
    v7 = 16;
  }
  if ( (a2 & 2) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://EnterpriseIds");
  }
  if ( (a2 & 4) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"PEDP://IntentEnterpriseId");
  }
  if ( (a2 & 8) != 0 )
  {
    v7 += 84;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://EvaluationFlags");
  }
  if ( (a2 & 0x10) != 0 )
  {
    v7 += 152;
    RtlInitUnicodeString(&DestinationString[v8++], L"EDP://ExemptEnterpriseIds");
  }
  while ( 1 )
  {
    if ( v6 )
      EnterpriseContextLibMemFree(v6);
    v6 = EnterpriseContextLibMemAllocPaged(v7);
    if ( !v6 )
      return (unsigned int)-1073741801;
    SecurityAttributesToken = NtQuerySecurityAttributesToken(*a1, DestinationString, v8, v6, v7, v12);
    v10 = SecurityAttributesToken;
    if ( SecurityAttributesToken != -1073741789 )
    {
      if ( SecurityAttributesToken == -1073741275 )
      {
        EnterpriseContextLibMemFree(v6);
        v10 = 0;
        *a3 = 0;
        return v10;
      }
      if ( SecurityAttributesToken >= 0 )
      {
        *a3 = v6;
        return v10;
      }
LABEL_22:
      EnterpriseContextLibMemFree(v6);
      return v10;
    }
    if ( v7 >= v12[0] )
      goto LABEL_22;
    v7 = v12[0];
  }
}

```

## disassembly

```asm
0x1800b1e8c  mov     [rsp+arg_8], rbx
0x1800b1e91  push    rbp
0x1800b1e92  push    rsi
0x1800b1e93  push    rdi
0x1800b1e94  push    r14
0x1800b1e96  push    r15
0x1800b1e98  sub     rsp, 90h
0x1800b1e9f  mov     rax, cs:__security_cookie
0x1800b1ea6  xor     rax, rsp
0x1800b1ea9  mov     [rsp+0B8h+var_38], rax
0x1800b1eb1  mov     esi, edx
0x1800b1eb3  mov     r14, r8
0x1800b1eb6  xor     edx, edx; Val
0x1800b1eb8  mov     r15, rcx
0x1800b1ebb  lea     rcx, [rsp+0B8h+DestinationString]; void *
0x1800b1ec0  lea     r8d, [rdx+40h]; Size
0x1800b1ec4  call    memset_0
0x1800b1ec9  xor     ebp, ebp
0x1800b1ecb  mov     [rsp+0B8h+var_88], ebp
0x1800b1ecf  mov     [r14], rbp
0x1800b1ed2  test    sil, 1
0x1800b1ed6  jz      short loc_1800B1EF8
0x1800b1ed8  lea     rdx, SourceString; "EDP://PolicyFlags"
0x1800b1edf  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x1800b1ee4  lea     ebx, [rbp+64h]
0x1800b1ee7  call    cs:__imp_RtlInitUnicodeString
0x1800b1eee  nop     dword ptr [rax+rax+00h]
0x1800b1ef3  lea     edi, [rbp+1]
0x1800b1ef6  jmp     short loc_1800B1EFD
0x1800b1ef8  xor     edi, edi
0x1800b1efa  lea     ebx, [rdi+10h]
0x1800b1efd  test    sil, 2
0x1800b1f01  jz      short loc_1800B1F2C
0x1800b1f03  mov     eax, edi
0x1800b1f05  lea     rcx, [rsp+0B8h+DestinationString]
0x1800b1f0a  shl     rax, 4
0x1800b1f0e  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x1800b1f15  add     rcx, rax; DestinationString
0x1800b1f18  add     ebx, 98h
0x1800b1f1e  call    cs:__imp_RtlInitUnicodeString
0x1800b1f25  nop     dword ptr [rax+rax+00h]
0x1800b1f2a  inc     edi
0x1800b1f2c  test    sil, 4
0x1800b1f30  jz      short loc_1800B1F5B
0x1800b1f32  mov     eax, edi
0x1800b1f34  lea     rcx, [rsp+0B8h+DestinationString]
0x1800b1f39  shl     rax, 4
0x1800b1f3d  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x1800b1f44  add     rcx, rax; DestinationString
0x1800b1f47  add     ebx, 98h
0x1800b1f4d  call    cs:__imp_RtlInitUnicodeString
0x1800b1f54  nop     dword ptr [rax+rax+00h]
0x1800b1f59  inc     edi
0x1800b1f5b  test    sil, 8
0x1800b1f5f  jz      short loc_1800B1F87
0x1800b1f61  mov     eax, edi
0x1800b1f63  lea     rcx, [rsp+0B8h+DestinationString]
0x1800b1f68  shl     rax, 4
0x1800b1f6c  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1800b1f73  add     rcx, rax; DestinationString
0x1800b1f76  add     ebx, 54h ; 'T'
0x1800b1f79  call    cs:__imp_RtlInitUnicodeString
0x1800b1f80  nop     dword ptr [rax+rax+00h]
0x1800b1f85  inc     edi
0x1800b1f87  test    sil, 10h
0x1800b1f8b  jz      short loc_1800B1FB6
0x1800b1f8d  mov     eax, edi
0x1800b1f8f  lea     rcx, [rsp+0B8h+DestinationString]
0x1800b1f94  shl     rax, 4
0x1800b1f98  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x1800b1f9f  add     rcx, rax; DestinationString
0x1800b1fa2  add     ebx, 98h
0x1800b1fa8  call    cs:__imp_RtlInitUnicodeString
0x1800b1faf  nop     dword ptr [rax+rax+00h]
0x1800b1fb4  inc     edi
0x1800b1fb6  test    rbp, rbp
0x1800b1fb9  jz      short loc_1800B1FC3
0x1800b1fbb  mov     rcx, rbp
0x1800b1fbe  call    EnterpriseContextLibMemFree
0x1800b1fc3  mov     ecx, ebx
0x1800b1fc5  call    EnterpriseContextLibMemAllocPaged
0x1800b1fca  mov     rbp, rax
0x1800b1fcd  test    rax, rax
0x1800b1fd0  jz      short loc_1800B2038
0x1800b1fd2  mov     rcx, [r15]
0x1800b1fd5  lea     rax, [rsp+0B8h+var_88]
0x1800b1fda  mov     [rsp+0B8h+var_90], rax
0x1800b1fdf  lea     rdx, [rsp+0B8h+DestinationString]
0x1800b1fe4  mov     r9, rbp
0x1800b1fe7  mov     [rsp+0B8h+var_98], ebx
0x1800b1feb  mov     r8d, edi
0x1800b1fee  call    cs:__imp_NtQuerySecurityAttributesToken
0x1800b1ff5  nop     dword ptr [rax+rax+00h]
0x1800b1ffa  mov     esi, eax
0x1800b1ffc  cmp     eax, 0C0000023h
0x1800b2001  jnz     short loc_1800B200F
0x1800b2003  cmp     ebx, [rsp+0B8h+var_88]
0x1800b2007  jnb     short loc_1800B202E
0x1800b2009  mov     ebx, [rsp+0B8h+var_88]
0x1800b200d  jmp     short loc_1800B1FB6
0x1800b200f  cmp     eax, 0C0000225h
0x1800b2014  jnz     short loc_1800B2025
0x1800b2016  mov     rcx, rbp
0x1800b2019  call    EnterpriseContextLibMemFree
0x1800b201e  xor     esi, esi
0x1800b2020  mov     [r14], rsi
0x1800b2023  jmp     short loc_1800B203D
0x1800b2025  test    eax, eax
0x1800b2027  js      short loc_1800B202E
0x1800b2029  mov     [r14], rbp
0x1800b202c  jmp     short loc_1800B203D
0x1800b202e  mov     rcx, rbp
0x1800b2031  call    EnterpriseContextLibMemFree
0x1800b2036  jmp     short loc_1800B203D
0x1800b2038  mov     esi, 0C0000017h
0x1800b203d  mov     eax, esi
0x1800b203f  mov     rcx, [rsp+0B8h+var_38]
0x1800b2047  xor     rcx, rsp; StackCookie
0x1800b204a  call    __security_check_cookie
0x1800b204f  mov     rbx, [rsp+0B8h+arg_8]
0x1800b2057  add     rsp, 90h
0x1800b205e  pop     r15
0x1800b2060  pop     r14
0x1800b2062  pop     rdi
0x1800b2063  pop     rsi
0x1800b2064  pop     rbp
0x1800b2065  retn
```
