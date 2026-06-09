# QueryAttributes

- ea: `0x1800178d0`
- end: `0x180017aab`
- name: `QueryAttributes`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017ab4`

## callees

- `0x180001c60`
- `0x1800026d8`
- `0x180017760`
- `0x180017784`
- `0x1800178d0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001792b`
- `ntdll!RtlInitUnicodeString` at `0x180017962`
- `ntdll!RtlInitUnicodeString` at `0x180017991`
- `ntdll!RtlInitUnicodeString` at `0x1800179bd`
- `ntdll!RtlInitUnicodeString` at `0x1800179ec`
- `ntdll!RtlInitUnicodeString` at `0x18001792b`
- `ntdll!RtlInitUnicodeString` at `0x180017962`
- `ntdll!RtlInitUnicodeString` at `0x180017991`
- `ntdll!RtlInitUnicodeString` at `0x1800179bd`
- `ntdll!RtlInitUnicodeString` at `0x1800179ec`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180017a32`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180017a32`

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
0x1800178d0  mov     [rsp+arg_8], rbx
0x1800178d5  push    rbp
0x1800178d6  push    rsi
0x1800178d7  push    rdi
0x1800178d8  push    r14
0x1800178da  push    r15
0x1800178dc  sub     rsp, 90h
0x1800178e3  mov     rax, cs:__security_cookie
0x1800178ea  xor     rax, rsp
0x1800178ed  mov     [rsp+0B8h+var_38], rax
0x1800178f5  mov     esi, edx
0x1800178f7  mov     r14, r8
0x1800178fa  xor     edx, edx; Val
0x1800178fc  mov     r15, rcx
0x1800178ff  lea     rcx, [rsp+0B8h+DestinationString]; void *
0x180017904  lea     r8d, [rdx+40h]; Size
0x180017908  call    memset_0
0x18001790d  xor     ebp, ebp
0x18001790f  mov     [rsp+0B8h+var_88], ebp
0x180017913  mov     [r14], rbp
0x180017916  test    sil, 1
0x18001791a  jz      short loc_18001793C
0x18001791c  lea     rdx, SourceString; "EDP://PolicyFlags"
0x180017923  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x180017928  lea     ebx, [rbp+64h]
0x18001792b  call    cs:__imp_RtlInitUnicodeString
0x180017932  nop     dword ptr [rax+rax+00h]
0x180017937  lea     edi, [rbp+1]
0x18001793a  jmp     short loc_180017941
0x18001793c  xor     edi, edi
0x18001793e  lea     ebx, [rdi+10h]
0x180017941  test    sil, 2
0x180017945  jz      short loc_180017970
0x180017947  mov     eax, edi
0x180017949  lea     rcx, [rsp+0B8h+DestinationString]
0x18001794e  shl     rax, 4
0x180017952  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x180017959  add     rcx, rax; DestinationString
0x18001795c  add     ebx, 98h
0x180017962  call    cs:__imp_RtlInitUnicodeString
0x180017969  nop     dword ptr [rax+rax+00h]
0x18001796e  inc     edi
0x180017970  test    sil, 4
0x180017974  jz      short loc_18001799F
0x180017976  mov     eax, edi
0x180017978  lea     rcx, [rsp+0B8h+DestinationString]
0x18001797d  shl     rax, 4
0x180017981  lea     rdx, aPedpIntentente; "PEDP://IntentEnterpriseId"
0x180017988  add     rcx, rax; DestinationString
0x18001798b  add     ebx, 98h
0x180017991  call    cs:__imp_RtlInitUnicodeString
0x180017998  nop     dword ptr [rax+rax+00h]
0x18001799d  inc     edi
0x18001799f  test    sil, 8
0x1800179a3  jz      short loc_1800179CB
0x1800179a5  mov     eax, edi
0x1800179a7  lea     rcx, [rsp+0B8h+DestinationString]
0x1800179ac  shl     rax, 4
0x1800179b0  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x1800179b7  add     rcx, rax; DestinationString
0x1800179ba  add     ebx, 54h ; 'T'
0x1800179bd  call    cs:__imp_RtlInitUnicodeString
0x1800179c4  nop     dword ptr [rax+rax+00h]
0x1800179c9  inc     edi
0x1800179cb  test    sil, 10h
0x1800179cf  jz      short loc_1800179FA
0x1800179d1  mov     eax, edi
0x1800179d3  lea     rcx, [rsp+0B8h+DestinationString]
0x1800179d8  shl     rax, 4
0x1800179dc  lea     rdx, aEdpExemptenter; "EDP://ExemptEnterpriseIds"
0x1800179e3  add     rcx, rax; DestinationString
0x1800179e6  add     ebx, 98h
0x1800179ec  call    cs:__imp_RtlInitUnicodeString
0x1800179f3  nop     dword ptr [rax+rax+00h]
0x1800179f8  inc     edi
0x1800179fa  test    rbp, rbp
0x1800179fd  jz      short loc_180017A07
0x1800179ff  mov     rcx, rbp
0x180017a02  call    EnterpriseContextLibMemFree
0x180017a07  mov     ecx, ebx
0x180017a09  call    EnterpriseContextLibMemAllocPaged
0x180017a0e  mov     rbp, rax
0x180017a11  test    rax, rax
0x180017a14  jz      short loc_180017A7C
0x180017a16  mov     rcx, [r15]
0x180017a19  lea     rax, [rsp+0B8h+var_88]
0x180017a1e  mov     [rsp+0B8h+var_90], rax
0x180017a23  lea     rdx, [rsp+0B8h+DestinationString]
0x180017a28  mov     r9, rbp
0x180017a2b  mov     [rsp+0B8h+var_98], ebx
0x180017a2f  mov     r8d, edi
0x180017a32  call    cs:__imp_NtQuerySecurityAttributesToken
0x180017a39  nop     dword ptr [rax+rax+00h]
0x180017a3e  mov     esi, eax
0x180017a40  cmp     eax, 0C0000023h
0x180017a45  jnz     short loc_180017A53
0x180017a47  cmp     ebx, [rsp+0B8h+var_88]
0x180017a4b  jnb     short loc_180017A72
0x180017a4d  mov     ebx, [rsp+0B8h+var_88]
0x180017a51  jmp     short loc_1800179FA
0x180017a53  cmp     eax, 0C0000225h
0x180017a58  jnz     short loc_180017A69
0x180017a5a  mov     rcx, rbp
0x180017a5d  call    EnterpriseContextLibMemFree
0x180017a62  xor     esi, esi
0x180017a64  mov     [r14], rsi
0x180017a67  jmp     short loc_180017A81
0x180017a69  test    eax, eax
0x180017a6b  js      short loc_180017A72
0x180017a6d  mov     [r14], rbp
0x180017a70  jmp     short loc_180017A81
0x180017a72  mov     rcx, rbp
0x180017a75  call    EnterpriseContextLibMemFree
0x180017a7a  jmp     short loc_180017A81
0x180017a7c  mov     esi, 0C0000017h
0x180017a81  mov     eax, esi
0x180017a83  mov     rcx, [rsp+0B8h+var_38]
0x180017a8b  xor     rcx, rsp; StackCookie
0x180017a8e  call    __security_check_cookie
0x180017a93  mov     rbx, [rsp+0B8h+arg_8]
0x180017a9b  add     rsp, 90h
0x180017aa2  pop     r15
0x180017aa4  pop     r14
0x180017aa6  pop     rdi
0x180017aa7  pop     rsi
0x180017aa8  pop     rbp
0x180017aa9  retn
```
