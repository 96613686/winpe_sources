# CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(void *,bool,ushort * *)

- ea: `0x18000ada8`
- end: `0x18000af8e`
- name: `?_s_GetLockScreenHistoryOrderInternal@CLockScreenHistory@@KAJPEAX_NPEAPEAG@Z`
- size: `486`
- prototype: `__int64 __fastcall(void *, bool, unsigned __int16 **)`
- caller_count: `10`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009320`
- `0x18000bf20`
- `0x180034230`
- `0x1800358d0`
- `0x18003fe54`
- `0x18004de24`
- `0x18004dfb4`
- `0x18004f68c`
- `0x1800b472c`
- `0x1800b91f4`

## callees

- `0x18000ada8`
- `0x18000af94`
- `0x18000d2b8`
- `0x18000d340`
- `0x180023fb0`
- `0x18003aa84`
- `0x180050ba0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000aebe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000aebe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aee2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aee2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000adf9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000adf9`

## string_xrefs

- `0x18000ae26`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SystemProtectedUserData`

## pseudocode

```c
__int64 __fastcall CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(void *a1, char a2, unsigned __int16 **a3)
{
  bool v5; // r14
  WCHAR *v6; // rbp
  int Error; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // ebx
  int v11; // esi
  int v12; // r9d
  int v13; // eax
  __int64 v14; // rax
  unsigned int i; // eax
  LPWSTR StringSid; // [rsp+40h] [rbp-258h] BYREF
  void *v18; // [rsp+48h] [rbp-250h] BYREF
  unsigned __int16 v19[264]; // [rsp+50h] [rbp-248h] BYREF

  v5 = 1;
  if ( a3 )
    *a3 = 0;
  v18 = 0;
  v6 = 0;
  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) || (Error = ResultFromKnownLastError(), v10 = Error, Error >= 0) )
  {
    v10 = StringCchPrintfW(
            v19,
            0x104u,
            L"%s\\%s\\%s\\%s",
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SystemProtectedUserData",
            StringSid);
    if ( v10 >= 0 )
    {
      v13 = SHRegAllocData(HKEY_LOCAL_MACHINE, v19, &Class, v12, &v18, (unsigned int *)L"AnyoneRead");
      v6 = (WCHAR *)v18;
      v10 = v13;
    }
    LocalFree(StringSid);
    v11 = v10;
    if ( v10 < 0 )
      goto LABEL_17;
    v8 = -1;
    v14 = -1;
    do
      ++v14;
    while ( v6[v14] );
    if ( v14 == 6 )
    {
      v5 = CompareStringOrdinal(v6, -1, L"ZYXWVU", -1, 0) == 2;
      if ( a3 )
      {
        *a3 = v6;
        goto LABEL_15;
      }
    }
    else if ( a3 )
    {
LABEL_15:
      if ( *a3 )
        goto LABEL_19;
    }
    CoTaskMemFree(v6);
    goto LABEL_17;
  }
  v11 = Error;
LABEL_17:
  if ( !a3 )
    goto LABEL_22;
  if ( !*a3 )
  {
LABEL_21:
    v11 = _AllocString<CTCoAllocPolicy>(v9, v8, L"ZYXWVU", a3);
    goto LABEL_22;
  }
LABEL_19:
  v9 = 0x80000000LL;
  if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147024882 )
    goto LABEL_21;
LABEL_22:
  if ( a2 && a3 && (int)LockScreenPathFromPolicy(0) >= 0 )
  {
    for ( i = 0; i < 6; ++i )
    {
      if ( (*a3)[i] == word_18012D7E0[0] )
      {
        (*a3)[i] = 80;
        break;
      }
    }
  }
  if ( v11 >= 0 )
    return v5;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000ada8  mov     [rsp+arg_8], rbx
0x18000adad  mov     [rsp+arg_18], rbp
0x18000adb2  push    rsi
0x18000adb3  push    rdi
0x18000adb4  push    r12
0x18000adb6  push    r14
0x18000adb8  push    r15
0x18000adba  sub     rsp, 270h
0x18000adc1  mov     rax, cs:__security_cookie
0x18000adc8  xor     rax, rsp
0x18000adcb  mov     [rsp+298h+var_38], rax
0x18000add3  xor     r12d, r12d
0x18000add6  mov     rdi, r8
0x18000add9  mov     r15b, dl
0x18000addc  mov     r14b, 1
0x18000addf  test    r8, r8
0x18000ade2  jz      short loc_18000ADE7
0x18000ade4  mov     [r8], r12
0x18000ade7  lea     rdx, [rsp+298h+StringSid]; StringSid
0x18000adec  mov     [rsp+298h+var_250], r12
0x18000adf1  mov     rbp, r12
0x18000adf4  mov     [rsp+298h+StringSid], r12
0x18000adf9  call    cs:__imp_ConvertSidToStringSidW
0x18000adff  test    eax, eax
0x18000ae01  jnz     short loc_18000AE15
0x18000ae03  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000ae08  mov     ebx, eax
0x18000ae0a  test    eax, eax
0x18000ae0c  jns     short loc_18000AE15
0x18000ae0e  mov     esi, eax
0x18000ae10  jmp     loc_18000AEE8
0x18000ae15  mov     rcx, [rsp+298h+StringSid]
0x18000ae1a  lea     rax, aLockscreen; "LockScreen"
0x18000ae21  mov     [rsp+298h+var_268], rax
0x18000ae26  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000ae2d  mov     rax, cs:off_1800E67F8; "AnyoneRead"
0x18000ae34  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x18000ae3b  mov     [rsp+298h+var_270], rax; unsigned int *
0x18000ae40  mov     edx, 104h; unsigned __int64
0x18000ae45  mov     qword ptr [rsp+298h+bIgnoreCase], rcx
0x18000ae4a  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x18000ae4f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ae54  mov     ebx, eax
0x18000ae56  test    eax, eax
0x18000ae58  js      short loc_18000AE83
0x18000ae5a  lea     rax, [rsp+298h+var_250]
0x18000ae5f  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18000ae66  lea     r8, Class; unsigned __int16 *
0x18000ae6d  mov     qword ptr [rsp+298h+bIgnoreCase], rax; void **
0x18000ae72  lea     rdx, [rsp+298h+var_248]; unsigned __int16 *
0x18000ae77  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18000ae7c  mov     rbp, [rsp+298h+var_250]
0x18000ae81  mov     ebx, eax
0x18000ae83  mov     rcx, [rsp+298h+StringSid]; hMem
0x18000ae88  call    cs:__imp_LocalFree
0x18000ae8e  mov     esi, ebx
0x18000ae90  test    ebx, ebx
0x18000ae92  js      short loc_18000AEE8
0x18000ae94  or      rdx, 0FFFFFFFFFFFFFFFFh; cchCount1
0x18000ae98  mov     rax, rdx
0x18000ae9b  inc     rax
0x18000ae9e  cmp     [rbp+rax*2+0], r12w
0x18000aea4  jnz     short loc_18000AE9B
0x18000aea6  cmp     rax, 6
0x18000aeaa  jnz     short loc_18000AED5
0x18000aeac  mov     r9d, edx; cchCount2
0x18000aeaf  mov     [rsp+298h+bIgnoreCase], r12d; bIgnoreCase
0x18000aeb4  lea     r8, String2; "ZYXWVU"
0x18000aebb  mov     rcx, rbp; lpString1
0x18000aebe  call    cs:__imp_CompareStringOrdinal
0x18000aec4  cmp     eax, 2
0x18000aec7  setz    r14b
0x18000aecb  test    rdi, rdi
0x18000aece  jz      short loc_18000AEDF
0x18000aed0  mov     [rdi], rbp
0x18000aed3  jmp     short loc_18000AEDA
0x18000aed5  test    rdi, rdi
0x18000aed8  jz      short loc_18000AEDF
0x18000aeda  cmp     [rdi], r12
0x18000aedd  jnz     short loc_18000AEF2
0x18000aedf  mov     rcx, rbp; pv
0x18000aee2  call    cs:__imp_CoTaskMemFree
0x18000aee8  test    rdi, rdi
0x18000aeeb  jz      short loc_18000AF17
0x18000aeed  cmp     [rdi], r12
0x18000aef0  jz      short loc_18000AF06
0x18000aef2  mov     ecx, 80000000h
0x18000aef7  lea     eax, [rbx+rcx]
0x18000aefa  test    ecx, eax
0x18000aefc  jnz     short loc_18000AF17
0x18000aefe  cmp     ebx, 8007000Eh
0x18000af04  jz      short loc_18000AF17
0x18000af06  mov     r9, rdi
0x18000af09  lea     r8, String2; "ZYXWVU"
0x18000af10  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000af15  mov     esi, eax
0x18000af17  test    r15b, r15b
0x18000af1a  jz      short loc_18000AF52
0x18000af1c  test    rdi, rdi
0x18000af1f  jz      short loc_18000AF52
0x18000af21  xor     ecx, ecx; unsigned __int16 **
0x18000af23  call    ?LockScreenPathFromPolicy@@YAJPEAPEAG@Z; LockScreenPathFromPolicy(ushort * *)
0x18000af28  test    eax, eax
0x18000af2a  js      short loc_18000AF52
0x18000af2c  movzx   r8d, cs:word_18012D7E0
0x18000af34  mov     eax, r12d
0x18000af37  cmp     eax, 6
0x18000af3a  jnb     short loc_18000AF52
0x18000af3c  mov     rdx, [rdi]
0x18000af3f  mov     ecx, eax
0x18000af41  cmp     [rdx+rcx*2], r8w
0x18000af46  jz      short loc_18000AF4C
0x18000af48  inc     eax
0x18000af4a  jmp     short loc_18000AF37
0x18000af4c  mov     word ptr [rdx+rcx*2], 50h ; 'P'
0x18000af52  test    esi, esi
0x18000af54  js      short loc_18000AF60
0x18000af56  test    r14b, r14b
0x18000af59  mov     esi, r12d
0x18000af5c  setnz   sil
0x18000af60  mov     eax, esi
0x18000af62  mov     rcx, [rsp+298h+var_38]
0x18000af6a  xor     rcx, rsp; StackCookie
0x18000af6d  call    __security_check_cookie
0x18000af72  lea     r11, [rsp+298h+var_28]
0x18000af7a  mov     rbx, [r11+38h]
0x18000af7e  mov     rbp, [r11+48h]
0x18000af82  mov     rsp, r11
0x18000af85  pop     r15
0x18000af87  pop     r14
0x18000af89  pop     r12
0x18000af8b  pop     rdi
0x18000af8c  pop     rsi
0x18000af8d  retn
```
