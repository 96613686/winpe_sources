# localComposeRecoveryKeyProvisioningMessageTpm_20

- ea: `0x1800550b8`
- end: `0x18005523c`
- name: `localComposeRecoveryKeyProvisioningMessageTpm_20`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180054cd4`

## callees

- `0x180017ad0`
- `0x180018194`
- `0x18002bf50`
- `0x18003d174`
- `0x18003d3bc`
- `0x1800550b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055157`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180055147`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180055147`

## pseudocode

```c
__int64 __fastcall localComposeRecoveryKeyProvisioningMessageTpm_20(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  __int64 v7; // rbx
  unsigned int v9; // ebx
  unsigned int *v10; // rdi
  signed int LastError; // eax
  unsigned int v12; // ebx
  unsigned __int8 *v13; // rdx
  __int64 v14; // rcx
  errno_t v15; // eax
  unsigned int *v16; // [rsp+30h] [rbp-38h] BYREF
  int v17; // [rsp+38h] [rbp-30h]
  unsigned int v18; // [rsp+70h] [rbp+8h] BYREF

  if ( *(_QWORD *)(a1 + 8) == *(_QWORD *)a1 )
    return 2147942487LL;
  v7 = *(_QWORD *)(a2 + 8) - *(_QWORD *)a2;
  if ( !v7 || a3[1] != *a3 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  v9 = v7 + 96;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(
    &v16,
    v9);
  v10 = v16;
  *v16 = 96;
  v10[1] = v9;
  v10[2] = 2;
  v10[3] = 1;
  v10[4] = 2;
  if ( !CopySid(0x44u, v10 + 5, *(PSID *)a1) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_17;
    v13 = (unsigned __int8 *)qword_1800AD908;
LABEL_16:
    v18 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      v13,
      0,
      0,
      (__int64)&v18);
LABEL_17:
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v16);
    return v12;
  }
  v14 = *v10;
  *((_QWORD *)v10 + 11) = (unsigned int)(*(_DWORD *)(a2 + 8) - *(_DWORD *)a2);
  v15 = memcpy_s_0(
          (char *)v16 + v14,
          (unsigned int)(v17 - (_DWORD)v16 - v14),
          *(const void *const *)a2,
          *(_QWORD *)(a2 + 8) - *(_QWORD *)a2);
  v12 = v15;
  if ( v15 )
  {
    if ( v15 > 0 )
      v12 = (unsigned __int16)v15 | 0x80070000;
    if ( (unsigned int)dword_1800BE0B8 <= 2 )
      goto LABEL_17;
    v13 = (unsigned __int8 *)&dword_1800AD854;
    goto LABEL_16;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::operator=(a4, &v16);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v16);
  return 0;
}

```

## disassembly

```asm
0x1800550b8  mov     [rsp+arg_8], rbx
0x1800550bd  mov     [rsp+arg_10], rbp
0x1800550c2  push    rsi
0x1800550c3  push    rdi
0x1800550c4  push    r14
0x1800550c6  sub     rsp, 50h
0x1800550ca  mov     rax, [rcx+8]
0x1800550ce  mov     rbp, r9
0x1800550d1  mov     rsi, rdx
0x1800550d4  mov     r14, rcx
0x1800550d7  cmp     rax, [rcx]
0x1800550da  jz      loc_180055221
0x1800550e0  mov     rbx, [rdx+8]
0x1800550e4  sub     rbx, [rdx]
0x1800550e7  jz      loc_180055221
0x1800550ed  mov     rax, [r8+8]
0x1800550f1  cmp     rax, [r8]
0x1800550f4  jnz     loc_180055221
0x1800550fa  test    r9, r9
0x1800550fd  jnz     short loc_180055109
0x1800550ff  mov     eax, 80004003h
0x180055104  jmp     loc_180055226
0x180055109  add     ebx, 60h ; '`'
0x18005510c  lea     rcx, [rsp+68h+var_38]
0x180055111  mov     edx, ebx
0x180055113  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@_KAEBU?$secure_allocator@E@wil@@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(unsigned __int64,wil::secure_allocator<uchar> const &)
0x180055118  mov     rdi, [rsp+68h+var_38]
0x18005511d  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x180055122  mov     dword ptr [rdi], 60h ; '`'
0x180055128  lea     rdx, [rdi+14h]; pDestinationSid
0x18005512c  mov     [rdi+4], ebx
0x18005512f  mov     dword ptr [rdi+8], 2
0x180055136  mov     dword ptr [rdi+0Ch], 1
0x18005513d  mov     dword ptr [rdi+10h], 2
0x180055144  mov     r8, [r14]; pSourceSid
0x180055147  call    cs:__imp_CopySid
0x18005514e  nop     dword ptr [rax+rax+00h]
0x180055153  test    eax, eax
0x180055155  jnz     short loc_180055186
0x180055157  call    cs:__imp_GetLastError
0x18005515e  nop     dword ptr [rax+rax+00h]
0x180055163  mov     ebx, eax
0x180055165  test    eax, eax
0x180055167  jle     short loc_180055172
0x180055169  movzx   ebx, ax
0x18005516c  or      ebx, 80070000h
0x180055172  mov     eax, cs:dword_1800BE0B8
0x180055178  cmp     eax, 2
0x18005517b  jbe     short loc_1800551F8
0x18005517d  lea     rdx, qword_1800AD908
0x180055184  jmp     short loc_1800551D8
0x180055186  mov     eax, [rsi+8]
0x180055189  sub     eax, [rsi]
0x18005518b  mov     ecx, [rdi]
0x18005518d  mov     [rdi+58h], eax
0x180055190  mov     dword ptr [rdi+5Ch], 0
0x180055197  mov     edx, [rsp+68h+var_30]
0x18005519b  sub     edx, dword ptr [rsp+68h+var_38]
0x18005519f  mov     r9, [rsi+8]
0x1800551a3  sub     edx, ecx; DestinationSize
0x1800551a5  add     rcx, [rsp+68h+var_38]; Destination
0x1800551aa  sub     r9, [rsi]; SourceSize
0x1800551ad  mov     r8, [rsi]; Source
0x1800551b0  call    memcpy_s_0
0x1800551b5  mov     ebx, eax
0x1800551b7  test    eax, eax
0x1800551b9  jz      short loc_180055206
0x1800551bb  jle     short loc_1800551C6
0x1800551bd  movzx   ebx, ax
0x1800551c0  or      ebx, 80070000h
0x1800551c6  mov     eax, cs:dword_1800BE0B8
0x1800551cc  cmp     eax, 2
0x1800551cf  jbe     short loc_1800551F8
0x1800551d1  lea     rdx, dword_1800AD854
0x1800551d8  lea     rax, [rsp+68h+arg_0]
0x1800551dd  mov     [rsp+68h+var_48], rax
0x1800551e2  xor     r9d, r9d
0x1800551e5  mov     [rsp+68h+arg_0], ebx
0x1800551e9  xor     r8d, r8d
0x1800551ec  lea     rcx, dword_1800BE0B8
0x1800551f3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800551f8  lea     rcx, [rsp+68h+var_38]
0x1800551fd  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x180055202  mov     eax, ebx
0x180055204  jmp     short loc_180055226
0x180055206  lea     rdx, [rsp+68h+var_38]
0x18005520b  mov     rcx, rbp
0x18005520e  call    ??4?$vector@EU?$secure_allocator@E@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar,wil::secure_allocator<uchar>>::operator=(std::vector<uchar,wil::secure_allocator<uchar>> &&)
0x180055213  lea     rcx, [rsp+68h+var_38]
0x180055218  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18005521d  xor     eax, eax
0x18005521f  jmp     short loc_180055226
0x180055221  mov     eax, 80070057h
0x180055226  lea     r11, [rsp+68h+var_18]
0x18005522b  mov     rbx, [r11+28h]
0x18005522f  mov     rbp, [r11+30h]
0x180055233  mov     rsp, r11
0x180055236  pop     r14
0x180055238  pop     rdi
0x180055239  pop     rsi
0x18005523a  retn
```
