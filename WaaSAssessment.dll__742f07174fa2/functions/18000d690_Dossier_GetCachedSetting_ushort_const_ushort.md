# Dossier::GetCachedSetting(ushort const *,ushort * *)

- ea: `0x18000d690`
- end: `0x18000d885`
- name: `?GetCachedSetting@Dossier@@EEAAJPEBGPEAPEAG@Z`
- size: `501`
- prototype: `int(Dossier *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e620`

## callees

- `0x18000d690`
- `0x18000efec`
- `0x180018948`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d6fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d78f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d7ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d82b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d83b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d854`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d6fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d737`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d78f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d7ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d82b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d83b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d854`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d7c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d7c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d76f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d811`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d76f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d811`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d705`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d705`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dossier::GetCachedSetting(Dossier *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int StateSeparationRegistryLocation; // edi
  unsigned __int16 *v6; // r15
  _QWORD *v7; // rsi
  void *v8; // r14
  DWORD LastError; // ebx
  LSTATUS ValueW; // eax
  unsigned int v12; // ebx
  SIZE_T v13; // rbx
  _WORD *v14; // rax
  void *pvData; // rdi
  _WORD *i; // rdx
  LSTATUS v17; // eax
  int pdwType; // [rsp+20h] [rbp-48h]
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-20h]
  unsigned __int16 *v21; // [rsp+50h] [rbp-18h] BYREF
  char v22; // [rsp+58h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  DWORD pcbData; // [rsp+C8h] [rbp+60h] BYREF

  pcbData = 0;
  pv = 0;
  p_pv = &pv;
  v21 = 0;
  v22 = 1;
  StateSeparationRegistryLocation = GetStateSeparationRegistryLocation(
                                      L"WaaSAssessment",
                                      L"Software\\Microsoft\\Windows\\CurrentVersion\\WaaSAssessment",
                                      &v21);
  if ( v22 )
  {
    v6 = v21;
    v7 = p_pv;
    v8 = *p_pv;
    if ( *p_pv )
    {
      LastError = GetLastError();
      CoTaskMemFree(v8);
      SetLastError(LastError);
    }
    *v7 = v6;
  }
  if ( StateSeparationRegistryLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)(unsigned int)StateSeparationRegistryLocation,
      pdwType);
    if ( pv )
      CoTaskMemFree(pv);
    return (unsigned int)StateSeparationRegistryLocation;
  }
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, (LPCWSTR)pv, a2, 2u, 0, 0, &pcbData);
  v12 = ValueW;
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v12 = (unsigned __int16)ValueW | 0x80070000;
    if ( pv )
      CoTaskMemFree(pv);
    return v12;
  }
  if ( pcbData )
  {
    v13 = pcbData;
    v14 = CoTaskMemAlloc(v13 * 2);
    pvData = v14;
    if ( v14 )
    {
      for ( i = &v14[v13]; v14 != i; ++v14 )
        *v14 = 0;
      v17 = RegGetValueW(HKEY_LOCAL_MACHINE, (LPCWSTR)pv, a2, 2u, 0, pvData, &pcbData);
      v12 = v17;
      if ( v17 )
      {
        if ( v17 > 0 )
          v12 = (unsigned __int16)v17 | 0x80070000;
        CoTaskMemFree(pvData);
        if ( pv )
          CoTaskMemFree(pv);
        return v12;
      }
      *a3 = (unsigned __int16 *)pvData;
      if ( pv )
        CoTaskMemFree(pv);
      return 0;
    }
    else
    {
      if ( pv )
        CoTaskMemFree(pv);
      return 2147942414LL;
    }
  }
  else
  {
    if ( pv )
      CoTaskMemFree(pv);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x18000d690  push    rbp
0x18000d692  push    rbx
0x18000d693  push    rsi
0x18000d694  push    rdi
0x18000d695  push    r12
0x18000d697  push    r13
0x18000d699  push    r14
0x18000d69b  push    r15
0x18000d69d  mov     rbp, rsp
0x18000d6a0  sub     rsp, 68h
0x18000d6a4  mov     r12, r8
0x18000d6a7  mov     r13, rdx
0x18000d6aa  xor     esi, esi
0x18000d6ac  mov     [rbp+arg_18], esi
0x18000d6af  mov     [rbp+pv], rsi
0x18000d6b3  lea     rax, [rbp+pv]
0x18000d6b7  mov     [rbp+var_20], rax
0x18000d6bb  mov     [rbp+var_18], rsi
0x18000d6bf  mov     [rbp+var_10], 1
0x18000d6c3  lea     r8, [rbp+var_18]; unsigned __int16 **
0x18000d6c7  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000d6ce  lea     rcx, aWaasassessment_2; "WaaSAssessment"
0x18000d6d5  call    ?GetStateSeparationRegistryLocation@@YAJPEBG0PEAPEAG@Z; GetStateSeparationRegistryLocation(ushort const *,ushort const *,ushort * *)
0x18000d6da  mov     edi, eax
0x18000d6dc  cmp     [rbp+var_10], sil
0x18000d6e0  jz      short loc_18000D711
0x18000d6e2  mov     r15, [rbp+var_18]
0x18000d6e6  mov     rsi, [rbp+var_20]
0x18000d6ea  mov     r14, [rsi]
0x18000d6ed  test    r14, r14
0x18000d6f0  jz      short loc_18000D70C
0x18000d6f2  call    cs:__imp_GetLastError
0x18000d6f8  mov     ebx, eax
0x18000d6fa  mov     rcx, r14; pv
0x18000d6fd  call    cs:__imp_CoTaskMemFree
0x18000d703  mov     ecx, ebx; dwErrCode
0x18000d705  call    cs:__imp_SetLastError
0x18000d70b  nop
0x18000d70c  mov     [rsi], r15
0x18000d70f  xor     esi, esi
0x18000d711  test    edi, edi
0x18000d713  jns     short loc_18000D745
0x18000d715  mov     rcx, [rbp+40h]; this
0x18000d719  mov     r9d, edi; char *
0x18000d71c  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000d723  mov     edx, 0A1h; void *
0x18000d728  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d72d  nop
0x18000d72e  mov     rcx, [rbp+pv]; pv
0x18000d732  test    rcx, rcx
0x18000d735  jz      short loc_18000D73E
0x18000d737  call    cs:__imp_CoTaskMemFree
0x18000d73d  nop
0x18000d73e  mov     eax, edi
0x18000d740  jmp     loc_18000D874
0x18000d745  lea     rax, [rbp+arg_18]
0x18000d749  mov     [rsp+68h+pcbData], rax; pcbData
0x18000d74e  mov     [rsp+68h+pvData], rsi; pvData
0x18000d753  mov     [rsp+68h+pdwType], rsi; pdwType
0x18000d758  mov     r9d, 2; dwFlags
0x18000d75e  mov     r8, r13; lpValue
0x18000d761  mov     rdx, [rbp+pv]; lpSubKey
0x18000d765  mov     r14, 0FFFFFFFF80000002h
0x18000d76c  mov     rcx, r14; hkey
0x18000d76f  call    cs:__imp_RegGetValueW
0x18000d775  mov     ebx, eax
0x18000d777  test    eax, eax
0x18000d779  jz      short loc_18000D79D
0x18000d77b  jle     short loc_18000D786
0x18000d77d  movzx   ebx, ax
0x18000d780  or      ebx, 80070000h
0x18000d786  mov     rcx, [rbp+pv]; pv
0x18000d78a  test    rcx, rcx
0x18000d78d  jz      short loc_18000D796
0x18000d78f  call    cs:__imp_CoTaskMemFree
0x18000d795  nop
0x18000d796  mov     eax, ebx
0x18000d798  jmp     loc_18000D874
0x18000d79d  mov     eax, [rbp+arg_18]
0x18000d7a0  test    eax, eax
0x18000d7a2  jnz     short loc_18000D7BE
0x18000d7a4  mov     rcx, [rbp+pv]; pv
0x18000d7a8  test    rcx, rcx
0x18000d7ab  jz      short loc_18000D7B4
0x18000d7ad  call    cs:__imp_CoTaskMemFree
0x18000d7b3  nop
0x18000d7b4  mov     eax, 80070002h
0x18000d7b9  jmp     loc_18000D874
0x18000d7be  lea     rbx, [rax+rax]
0x18000d7c2  mov     rcx, rbx; cb
0x18000d7c5  call    cs:__imp_CoTaskMemAlloc
0x18000d7cb  mov     rdi, rax
0x18000d7ce  test    rax, rax
0x18000d7d1  jz      loc_18000D85F
0x18000d7d7  lea     rdx, [rbx+rax]
0x18000d7db  cmp     rax, rdx
0x18000d7de  jz      short loc_18000D7EE
0x18000d7e0  xor     ecx, ecx
0x18000d7e2  mov     [rax], cx
0x18000d7e5  add     rax, 2
0x18000d7e9  cmp     rax, rdx
0x18000d7ec  jnz     short loc_18000D7E0
0x18000d7ee  lea     rax, [rbp+arg_18]
0x18000d7f2  mov     [rsp+68h+pcbData], rax; pcbData
0x18000d7f7  mov     [rsp+68h+pvData], rdi; pvData
0x18000d7fc  mov     [rsp+68h+pdwType], rsi; pdwType
0x18000d801  mov     r9d, 2; dwFlags
0x18000d807  mov     r8, r13; lpValue
0x18000d80a  mov     rdx, [rbp+pv]; lpSubKey
0x18000d80e  mov     rcx, r14; hkey
0x18000d811  call    cs:__imp_RegGetValueW
0x18000d817  mov     ebx, eax
0x18000d819  test    eax, eax
0x18000d81b  jz      short loc_18000D847
0x18000d81d  jle     short loc_18000D828
0x18000d81f  movzx   ebx, ax
0x18000d822  or      ebx, 80070000h
0x18000d828  mov     rcx, rdi; pv
0x18000d82b  call    cs:__imp_CoTaskMemFree
0x18000d831  nop
0x18000d832  mov     rcx, [rbp+pv]; pv
0x18000d836  test    rcx, rcx
0x18000d839  jz      short loc_18000D842
0x18000d83b  call    cs:__imp_CoTaskMemFree
0x18000d841  nop
0x18000d842  jmp     loc_18000D796
0x18000d847  mov     [r12], rdi
0x18000d84b  mov     rcx, [rbp+pv]; pv
0x18000d84f  test    rcx, rcx
0x18000d852  jz      short loc_18000D85B
0x18000d854  call    cs:__imp_CoTaskMemFree
0x18000d85a  nop
0x18000d85b  xor     eax, eax
0x18000d85d  jmp     short loc_18000D874
0x18000d85f  mov     rcx, [rbp+pv]; pv
0x18000d863  test    rcx, rcx
0x18000d866  jz      short loc_18000D86F
0x18000d868  call    cs:__imp_CoTaskMemFree
0x18000d86e  nop
0x18000d86f  mov     eax, 8007000Eh
0x18000d874  add     rsp, 68h
0x18000d878  pop     r15
0x18000d87a  pop     r14
0x18000d87c  pop     r13
0x18000d87e  pop     r12
0x18000d880  pop     rdi
0x18000d881  pop     rsi
0x18000d882  pop     rbx
0x18000d883  pop     rbp
0x18000d884  retn
```
