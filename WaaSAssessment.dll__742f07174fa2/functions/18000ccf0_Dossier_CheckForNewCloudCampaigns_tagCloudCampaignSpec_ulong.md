# Dossier::CheckForNewCloudCampaigns(tagCloudCampaignSpec * *,ulong *)

- ea: `0x18000ccf0`
- end: `0x18000cfa5`
- name: `?CheckForNewCloudCampaigns@Dossier@@UEAAJPEAPEAUtagCloudCampaignSpec@@PEAK@Z`
- size: `693`
- prototype: `int(Dossier *__hidden this, struct tagCloudCampaignSpec **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000ccf0`
- `0x18000d2a8`
- `0x18000efec`
- `0x18001752c`
- `0x1800185b4`
- `0x18001973a`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cdaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cdaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ce30`

## string_xrefs

- `0x18000cd19`: `Cleaning up registry keys for cloud campaigns`
- `0x18000cd35`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\REMEDIATION\DTU\CloudSettings`
- `0x18000ce92`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\REMEDIATION\DTU\CloudSettings`
- `0x18000cd66`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\REMEDIATION\CANVAS\CloudSettings`
- `0x18000cee6`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\REMEDIATION\CANVAS\CloudSettings`

## pseudocode

```c
__int64 __fastcall Dossier::CheckForNewCloudCampaigns(
        Dossier *this,
        struct tagCloudCampaignSpec **a2,
        unsigned int *a3)
{
  HKEY v5; // rcx
  HKEY v6; // rcx
  int v7; // ebx
  __int64 v8; // rdx
  int v10; // edi
  struct WOSCKeyValuePair *v11; // rsi
  unsigned int v12; // eax
  unsigned int i; // ecx
  __int64 v14; // rax
  Dossier *v15; // rcx
  struct tagCloudCampaignSpec *v16; // rax
  int v17; // ebx
  const wchar_t *v18; // r12
  __int64 v19; // r13
  unsigned int j; // r14d
  int v21; // [rsp+20h] [rbp-30h]
  unsigned int v22; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v23[3]; // [rsp+44h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  unsigned int v26; // [rsp+A8h] [rbp+58h] BYREF

  v23[0] = 0;
  v22 = 0;
  v26 = 0;
  LogLevel(4u, L"Cleaning up registry keys for cloud campaigns");
  v7 = DeleteAllValuesInKey(
         v5,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\REMEDIATION\\DTU\\CloudSettings");
  if ( v7 < 0 )
  {
    v8 = 689;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
      (const char *)(unsigned int)v7,
      v21);
    return (unsigned int)v7;
  }
  v7 = DeleteAllValuesInKey(
         v6,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\REMEDIATION\\CANVAS\\CloudSettings");
  if ( v7 < 0 )
  {
    v8 = 690;
    goto LABEL_3;
  }
  v10 = (*(__int64 (__fastcall **)(Dossier *, _QWORD, unsigned int *))(*(_QWORD *)this + 8LL))(this, 0, v23);
  if ( v10 >= 0 && v23[0] )
  {
    v11 = (struct WOSCKeyValuePair *)CoTaskMemAlloc(16LL * v23[0]);
    if ( v11 )
    {
      LogLevel(4u, L"%d settings found for RUXIM", v23[0]);
      v12 = v23[0];
      for ( i = 0; i < v23[0]; v12 = v23[0] )
      {
        v14 = (int)i++;
        v14 *= 2;
        *((_QWORD *)v11 + v14) = 0;
        *((_QWORD *)v11 + v14 + 1) = 0;
      }
      v26 = v12;
      v10 = (*(__int64 (__fastcall **)(Dossier *, struct WOSCKeyValuePair *, unsigned int *))(*(_QWORD *)this + 8LL))(
              this,
              v11,
              &v26);
      if ( v10 >= 0 )
      {
        v16 = (struct tagCloudCampaignSpec *)CoTaskMemAlloc(16LL * v26);
        *a2 = v16;
        if ( v16 )
        {
          v17 = 0;
          if ( v26 )
          {
            while ( 1 )
            {
              v18 = (const wchar_t *)*((_QWORD *)v11 + 2 * v17);
              v19 = *((_QWORD *)v11 + 2 * v17 + 1);
              if ( !wcsncmp_0(v18, L"DTUSPEC", 7u) )
                v10 = (*(__int64 (__fastcall **)(Dossier *, const wchar_t *, __int64, _QWORD, const wchar_t *, const unsigned __int16 *, unsigned int *))(*(_QWORD *)this + 16LL))(
                        this,
                        v18,
                        v19,
                        *a2,
                        L"DTU",
                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\REMEDIATION\\DTU\\CloudSettings",
                        &v22);
              if ( !wcsncmp_0(v18, L"RUXIMSPEC", 9u) )
                v10 = (*(__int64 (__fastcall **)(Dossier *, const wchar_t *, __int64, _QWORD, const wchar_t *, const unsigned __int16 *, unsigned int *))(*(_QWORD *)this + 16LL))(
                        this,
                        v18,
                        v19,
                        *a2,
                        L"CANVAS",
                        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\REMEDIATION\\CANVAS\\CloudSettings",
                        &v22);
              if ( v10 < 0 )
                break;
              if ( ++v17 >= v26 )
                goto LABEL_22;
            }
            for ( j = 0; j < v22; ++j )
            {
              CoTaskMemFree(*(LPVOID *)a2[j]);
              CoTaskMemFree(*((LPVOID *)a2[j] + 1));
            }
            CoTaskMemFree(a2);
          }
          else
          {
LABEL_22:
            LogLevel(4u, L"%d cloud campaigns found", v22);
            v15 = (Dossier *)a3;
            *a3 = v22;
          }
        }
        else
        {
          v10 = -2147024882;
        }
      }
      else
      {
        LogLevel(4u, L"Failed to get all key value pairs for RUXIM.");
      }
      Dossier::FreeKeyValuePairs(v15, v11, v26);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ccf0  mov     [rsp-38h+arg_0], rbx
0x18000ccf5  mov     [rsp-38h+arg_10], r8
0x18000ccfa  push    rbp
0x18000ccfb  push    rsi
0x18000ccfc  push    rdi
0x18000ccfd  push    r12
0x18000ccff  push    r13
0x18000cd01  push    r14
0x18000cd03  push    r15
0x18000cd05  mov     rbp, rsp
0x18000cd08  sub     rsp, 50h
0x18000cd0c  xor     r12d, r12d
0x18000cd0f  mov     r15, rdx
0x18000cd12  mov     r14, rcx
0x18000cd15  mov     [rbp+var_C], r12d
0x18000cd19  lea     rdx, aCleaningUpRegi; "Cleaning up registry keys for cloud cam"...
0x18000cd20  mov     [rbp+var_10], r12d
0x18000cd24  mov     [rbp+arg_18], r12d
0x18000cd28  lea     r13d, [r12+4]
0x18000cd2d  mov     ecx, r13d; unsigned __int8
0x18000cd30  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000cd35  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000cd3c  call    ?DeleteAllValuesInKey@@YAJPEAUHKEY__@@PEBG@Z; DeleteAllValuesInKey(HKEY__ *,ushort const *)
0x18000cd41  mov     ebx, eax
0x18000cd43  test    eax, eax
0x18000cd45  jns     short loc_18000CD66
0x18000cd47  mov     edx, 2B1h; void *
0x18000cd4c  mov     rcx, [rbp+38h]; this
0x18000cd50  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000cd57  mov     r9d, ebx; char *
0x18000cd5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd5f  mov     eax, ebx
0x18000cd61  jmp     loc_18000CF8D
0x18000cd66  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000cd6d  call    ?DeleteAllValuesInKey@@YAJPEAUHKEY__@@PEBG@Z; DeleteAllValuesInKey(HKEY__ *,ushort const *)
0x18000cd72  mov     ebx, eax
0x18000cd74  test    eax, eax
0x18000cd76  jns     short loc_18000CD7F
0x18000cd78  mov     edx, 2B2h
0x18000cd7d  jmp     short loc_18000CD4C
0x18000cd7f  mov     rax, [r14]
0x18000cd82  lea     r8, [rbp+var_C]
0x18000cd86  xor     edx, edx
0x18000cd88  mov     rcx, r14
0x18000cd8b  mov     rax, [rax+8]
0x18000cd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd94  mov     edi, eax
0x18000cd96  test    eax, eax
0x18000cd98  js      loc_18000CF8B
0x18000cd9e  mov     eax, [rbp+var_C]
0x18000cda1  test    eax, eax
0x18000cda3  jz      loc_18000CF8B
0x18000cda9  mov     ecx, eax
0x18000cdab  shl     rcx, 4; cb
0x18000cdaf  call    cs:__imp_CoTaskMemAlloc
0x18000cdb5  mov     rsi, rax
0x18000cdb8  test    rax, rax
0x18000cdbb  jz      loc_18000CF86
0x18000cdc1  mov     r8d, [rbp+var_C]
0x18000cdc5  lea     rdx, aDSettingsFound; "%d settings found for RUXIM"
0x18000cdcc  mov     ecx, r13d; unsigned __int8
0x18000cdcf  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000cdd4  mov     eax, [rbp+var_C]
0x18000cdd7  mov     ecx, r12d
0x18000cdda  test    eax, eax
0x18000cddc  jz      short loc_18000CDF6
0x18000cdde  movsxd  rax, ecx
0x18000cde1  inc     ecx
0x18000cde3  add     rax, rax
0x18000cde6  mov     [rsi+rax*8], r12
0x18000cdea  mov     [rsi+rax*8+8], r12
0x18000cdef  mov     eax, [rbp+var_C]
0x18000cdf2  cmp     ecx, eax
0x18000cdf4  jb      short loc_18000CDDE
0x18000cdf6  mov     [rbp+arg_18], eax
0x18000cdf9  lea     r8, [rbp+arg_18]
0x18000cdfd  mov     rax, [r14]
0x18000ce00  mov     rdx, rsi
0x18000ce03  mov     rcx, r14
0x18000ce06  mov     rax, [rax+8]
0x18000ce0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce0f  mov     edi, eax
0x18000ce11  test    eax, eax
0x18000ce13  jns     short loc_18000CE29
0x18000ce15  lea     rdx, aFailedToGetAll; "Failed to get all key value pairs for R"...
0x18000ce1c  mov     ecx, r13d; unsigned __int8
0x18000ce1f  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000ce24  jmp     loc_18000CF3D
0x18000ce29  mov     ecx, [rbp+arg_18]
0x18000ce2c  shl     rcx, 4; cb
0x18000ce30  call    cs:__imp_CoTaskMemAlloc
0x18000ce36  mov     [r15], rax
0x18000ce39  test    rax, rax
0x18000ce3c  jnz     short loc_18000CE48
0x18000ce3e  mov     edi, 8007000Eh
0x18000ce43  jmp     loc_18000CF3D
0x18000ce48  mov     ebx, r12d
0x18000ce4b  cmp     [rbp+arg_18], r12d
0x18000ce4f  jbe     loc_18000CF21
0x18000ce55  movsxd  rax, ebx
0x18000ce58  lea     rdx, aDtuspec; "DTUSPEC"
0x18000ce5f  add     rax, rax
0x18000ce62  mov     r8d, 7; MaxCount
0x18000ce68  mov     r12, [rsi+rax*8]
0x18000ce6c  mov     r13, [rsi+rax*8+8]
0x18000ce71  mov     rcx, r12; String1
0x18000ce74  call    wcsncmp_0
0x18000ce79  test    eax, eax
0x18000ce7b  jnz     short loc_18000CEB8
0x18000ce7d  mov     rax, [r14]
0x18000ce80  lea     rcx, [rbp+var_10]
0x18000ce84  mov     r9, [r15]
0x18000ce87  mov     r8, r13
0x18000ce8a  mov     [rsp+50h+var_20], rcx
0x18000ce8f  mov     rdx, r12
0x18000ce92  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000ce99  mov     rax, [rax+10h]
0x18000ce9d  mov     [rsp+50h+var_28], rcx
0x18000cea2  lea     rcx, aDtu; "DTU"
0x18000cea9  mov     [rsp+50h+var_30], rcx
0x18000ceae  mov     rcx, r14
0x18000ceb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ceb6  mov     edi, eax
0x18000ceb8  mov     r8d, 9; MaxCount
0x18000cebe  lea     rdx, aRuximspec; "RUXIMSPEC"
0x18000cec5  mov     rcx, r12; String1
0x18000cec8  call    wcsncmp_0
0x18000cecd  test    eax, eax
0x18000cecf  jnz     short loc_18000CF0C
0x18000ced1  mov     rax, [r14]
0x18000ced4  lea     rcx, [rbp+var_10]
0x18000ced8  mov     r9, [r15]
0x18000cedb  mov     r8, r13
0x18000cede  mov     [rsp+50h+var_20], rcx
0x18000cee3  mov     rdx, r12
0x18000cee6  lea     rcx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000ceed  mov     rax, [rax+10h]
0x18000cef1  mov     [rsp+50h+var_28], rcx
0x18000cef6  lea     rcx, aCanvas; "CANVAS"
0x18000cefd  mov     [rsp+50h+var_30], rcx
0x18000cf02  mov     rcx, r14
0x18000cf05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf0a  mov     edi, eax
0x18000cf0c  test    edi, edi
0x18000cf0e  js      short loc_18000CF4B
0x18000cf10  inc     ebx
0x18000cf12  cmp     ebx, [rbp+arg_18]
0x18000cf15  jb      loc_18000CE55
0x18000cf1b  mov     r13d, 4
0x18000cf21  mov     r8d, [rbp+var_10]
0x18000cf25  lea     rdx, aDCloudCampaign; "%d cloud campaigns found"
0x18000cf2c  mov     ecx, r13d; unsigned __int8
0x18000cf2f  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000cf34  mov     rcx, [rbp+arg_10]; this
0x18000cf38  mov     eax, [rbp+var_10]
0x18000cf3b  mov     [rcx], eax
0x18000cf3d  mov     r8d, [rbp+arg_18]; unsigned int
0x18000cf41  mov     rdx, rsi; struct WOSCKeyValuePair *
0x18000cf44  call    ?FreeKeyValuePairs@Dossier@@AEAAXPEAUWOSCKeyValuePair@@K@Z; Dossier::FreeKeyValuePairs(WOSCKeyValuePair *,ulong)
0x18000cf49  jmp     short loc_18000CF8B
0x18000cf4b  xor     r14d, r14d
0x18000cf4e  cmp     [rbp+var_10], r14d
0x18000cf52  jbe     short loc_18000CF7B
0x18000cf54  movsxd  rbx, r14d
0x18000cf57  mov     rcx, [r15+rbx*8]
0x18000cf5b  mov     rcx, [rcx]; pv
0x18000cf5e  call    cs:__imp_CoTaskMemFree
0x18000cf64  mov     rcx, [r15+rbx*8]
0x18000cf68  mov     rcx, [rcx+8]; pv
0x18000cf6c  call    cs:__imp_CoTaskMemFree
0x18000cf72  inc     r14d
0x18000cf75  cmp     r14d, [rbp+var_10]
0x18000cf79  jb      short loc_18000CF54
0x18000cf7b  mov     rcx, r15; pv
0x18000cf7e  call    cs:__imp_CoTaskMemFree
0x18000cf84  jmp     short loc_18000CF3D
0x18000cf86  mov     edi, 8007000Eh
0x18000cf8b  mov     eax, edi
0x18000cf8d  mov     rbx, [rsp+50h+arg_0]
0x18000cf95  add     rsp, 50h
0x18000cf99  pop     r15
0x18000cf9b  pop     r14
0x18000cf9d  pop     r13
0x18000cf9f  pop     r12
0x18000cfa1  pop     rdi
0x18000cfa2  pop     rsi
0x18000cfa3  pop     rbp
0x18000cfa4  retn
```
