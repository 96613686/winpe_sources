# WinReGetWimVersion

- ea: `0x1800237a0`
- end: `0x180023a12`
- name: `WinReGetWimVersion`
- size: `626`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18001ef18`
- `0x1800237a0`
- `0x18004d52c`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800237ee`
- `KERNEL32!SetLastError` at `0x1800239eb`
- `KERNEL32!SetLastError` at `0x1800237ee`
- `KERNEL32!SetLastError` at `0x1800239eb`
- `DismApi!DismInitialize` at `0x1800238bc`
- `DismApi!DismInitialize` at `0x1800238bc`
- `DismApi!DismShutdown` at `0x1800239b2`
- `DismApi!DismShutdown` at `0x1800239b2`
- `DismApi!DismDelete` at `0x18002399f`
- `DismApi!DismDelete` at `0x18002399f`
- `DismApi!DismGetImageInfo` at `0x1800238f6`
- `DismApi!DismGetImageInfo` at `0x1800238f6`

## string_xrefs

- `0x180023823`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`

## pseudocode

```c
__int64 __fastcall WinReGetWimVersion(unsigned __int16 *a1, unsigned int *a2, unsigned int *a3, _DWORD *a4, int *a5)
{
  int v10; // ebx
  unsigned int v11; // r14d
  DWORD DoesPathExist; // edi
  const wchar_t *v13; // rdx
  int ImageInfo; // ebp
  _DWORD *v15; // rcx
  int v16; // eax
  int v17; // [rsp+28h] [rbp-80h]
  _DWORD *v18; // [rsp+40h] [rbp-68h] BYREF
  int v19; // [rsp+48h] [rbp-60h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DumpWinREVersion>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_DumpWinREVersion>::GetImpl'::`2'::impl) )
  {
    SetLastError(0x32u);
    return 0;
  }
  v10 = 0;
  v18 = 0;
  v11 = 0;
  v19 = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReGetWimVersion");
  if ( a1 )
  {
    if ( !a2 || !a3 || !a4 || !a5 )
    {
      DoesPathExist = 87;
      UnattendLogW(1, L"Invalid output parameter");
      goto LABEL_23;
    }
    UnattendLogW(0, L"WIM file: %s", a1);
    DoesPathExist = Utils::DoesPathExist(a1);
    if ( DoesPathExist )
    {
      v13 = L"WIM file does not exist: %s";
LABEL_11:
      UnattendLogW(1, v13, a1);
      goto LABEL_23;
    }
    ImageInfo = DismInitialize(2, 0, 0);
    if ( ImageInfo >= 0 )
    {
      v10 = 1;
      ImageInfo = DismGetImageInfo(a1, &v18, &v19);
      if ( ImageInfo >= 0 )
      {
        if ( v19 )
        {
          v15 = v18;
          if ( v18 )
          {
            *a2 = v18[21];
            *a3 = v15[22];
            *a4 = v15[23];
            v17 = v15[24];
            *a5 = v17;
            UnattendLogW(0, L"WIM Version: %d.%d.%d.%d", *a2, *a3, *a4, v17);
            v11 = 1;
            goto LABEL_23;
          }
          DoesPathExist = 13;
          v13 = L"No image info returned from WIM file: %s";
        }
        else
        {
          DoesPathExist = 1168;
          v13 = L"No images found in WIM file: %s";
        }
        goto LABEL_11;
      }
      UnattendLogW(1, L"DismGetImageInfo() failed. Error: 0x%x", (unsigned int)ImageInfo);
    }
    else
    {
      UnattendLogW(1, L"WinReGetWimVersion failed to initialize DISM error 0x%x", (unsigned int)ImageInfo);
    }
    DoesPathExist = (unsigned __int16)ImageInfo;
    goto LABEL_23;
  }
  DoesPathExist = 8;
  UnattendLogW(
    2,
    L"WinReGetWimVersion %s (0x%x) in file %S line %d",
    L"Invalid wim file parameter",
    8,
    "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
    9418);
LABEL_23:
  if ( v18 )
  {
    DismDelete(v18);
    v18 = 0;
  }
  if ( v10 )
  {
    v16 = DismShutdown();
    if ( v16 < 0 )
      UnattendLogW(2, L"WinReGetWimVersion failed to shutdown DISM error 0x%x", (unsigned int)v16);
  }
  UnattendLogW(0, L"Exit WinReGetWimVersion return value: %d, last error: 0x%x", v11, DoesPathExist);
  UnattendFinalizeLog();
  SetLastError(DoesPathExist);
  return v11;
}

```

## disassembly

```asm
0x1800237a0  push    rbx
0x1800237a2  push    rbp
0x1800237a3  push    rsi
0x1800237a4  push    rdi
0x1800237a5  push    r12
0x1800237a7  push    r13
0x1800237a9  push    r14
0x1800237ab  push    r15
0x1800237ad  sub     rsp, 68h
0x1800237b1  mov     rax, cs:__security_cookie
0x1800237b8  xor     rax, rsp
0x1800237bb  mov     [rsp+0A8h+var_58], rax
0x1800237c0  mov     rdi, [rsp+0A8h+arg_20]
0x1800237c8  mov     r13, r9
0x1800237cb  mov     [rsp+0A8h+var_70], rdi
0x1800237d0  mov     r12, r8
0x1800237d3  mov     r15, rdx
0x1800237d6  mov     rsi, rcx
0x1800237d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_DumpWinREVersion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DumpWinREVersion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DumpWinREVersion> `wil::Feature<__WilFeatureTraits_Feature_Servicing_DumpWinREVersion>::GetImpl(void)'::`2'::impl
0x1800237e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_DumpWinREVersion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_DumpWinREVersion>::__private_IsEnabled(void)
0x1800237e5  test    al, al
0x1800237e7  jnz     short loc_1800237FB
0x1800237e9  mov     ecx, 32h ; '2'; dwErrCode
0x1800237ee  call    cs:__imp_SetLastError
0x1800237f4  xor     eax, eax
0x1800237f6  jmp     loc_1800239F4
0x1800237fb  xor     ebx, ebx
0x1800237fd  xor     ecx, ecx
0x1800237ff  mov     [rsp+0A8h+var_68], rbx
0x180023804  xor     r14d, r14d
0x180023807  mov     [rsp+0A8h+var_60], ebx
0x18002380b  call    UnattendInitializeLogEx2
0x180023810  lea     rdx, aEnterWinregetw; "Enter WinReGetWimVersion"
0x180023817  xor     ecx, ecx
0x180023819  call    UnattendLogW
0x18002381e  test    rsi, rsi
0x180023821  jnz     short loc_180023858
0x180023823  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002382a  mov     [rsp+0A8h+var_80], 24CAh
0x180023832  lea     edi, [rbx+8]
0x180023835  mov     [rsp+0A8h+var_88], rax
0x18002383a  mov     r9d, edi
0x18002383d  lea     r8, aInvalidWimFile; "Invalid wim file parameter"
0x180023844  lea     rdx, aWinregetwimver_0; "WinReGetWimVersion %s (0x%x) in file %S"...
0x18002384b  lea     ecx, [rbx+2]
0x18002384e  call    UnattendLogW
0x180023853  jmp     loc_180023995
0x180023858  test    r15, r15
0x18002385b  jz      loc_180023981
0x180023861  test    r12, r12
0x180023864  jz      loc_180023981
0x18002386a  test    r13, r13
0x18002386d  jz      loc_180023981
0x180023873  test    rdi, rdi
0x180023876  jz      loc_180023981
0x18002387c  mov     r8, rsi
0x18002387f  lea     rdx, aWimFileS; "WIM file: %s"
0x180023886  xor     ecx, ecx
0x180023888  call    UnattendLogW
0x18002388d  mov     rcx, rsi; unsigned __int16 *
0x180023890  call    ?DoesPathExist@Utils@@SAKPEBG@Z; Utils::DoesPathExist(ushort const *)
0x180023895  mov     edi, eax
0x180023897  test    eax, eax
0x180023899  jz      short loc_1800238B4
0x18002389b  lea     rdx, aWimFileDoesNot; "WIM file does not exist: %s"
0x1800238a2  mov     ecx, 1
0x1800238a7  mov     r8, rsi
0x1800238aa  call    UnattendLogW
0x1800238af  jmp     loc_180023995
0x1800238b4  xor     edx, edx
0x1800238b6  xor     r8d, r8d
0x1800238b9  lea     ecx, [rdx+2]
0x1800238bc  call    cs:__imp_DismInitialize
0x1800238c2  mov     ebp, eax
0x1800238c4  test    eax, eax
0x1800238c6  jns     short loc_1800238E4
0x1800238c8  lea     rdx, aWinregetwimver_2; "WinReGetWimVersion failed to initialize"...
0x1800238cf  mov     ecx, 1
0x1800238d4  mov     r8d, ebp
0x1800238d7  call    UnattendLogW
0x1800238dc  movzx   edi, bp
0x1800238df  jmp     loc_180023995
0x1800238e4  lea     r8, [rsp+0A8h+var_60]
0x1800238e9  mov     rcx, rsi
0x1800238ec  lea     rdx, [rsp+0A8h+var_68]
0x1800238f1  mov     ebx, 1
0x1800238f6  call    cs:__imp_DismGetImageInfo
0x1800238fc  mov     ebp, eax
0x1800238fe  test    eax, eax
0x180023900  js      short loc_180023973
0x180023902  cmp     [rsp+0A8h+var_60], r14d
0x180023907  jnz     short loc_180023919
0x180023909  mov     edi, 490h
0x18002390e  lea     rdx, aNoImagesFoundI; "No images found in WIM file: %s"
0x180023915  mov     ecx, ebx
0x180023917  jmp     short loc_1800238A7
0x180023919  mov     rcx, [rsp+0A8h+var_68]
0x18002391e  test    rcx, rcx
0x180023921  jnz     short loc_18002392F
0x180023923  lea     edi, [rcx+0Dh]
0x180023926  lea     rdx, aNoImageInfoRet; "No image info returned from WIM file: %"...
0x18002392d  jmp     short loc_180023915
0x18002392f  mov     eax, [rcx+54h]
0x180023932  lea     rdx, aWimVersionDDDD; "WIM Version: %d.%d.%d.%d"
0x180023939  mov     [r15], eax
0x18002393c  mov     eax, [rcx+58h]
0x18002393f  mov     [r12], eax
0x180023943  mov     eax, [rcx+5Ch]
0x180023946  mov     [r13+0], eax
0x18002394a  mov     eax, [rcx+60h]
0x18002394d  mov     rcx, [rsp+0A8h+var_70]
0x180023952  mov     [rsp+0A8h+var_80], eax
0x180023956  mov     [rcx], eax
0x180023958  xor     ecx, ecx
0x18002395a  mov     eax, [r13+0]
0x18002395e  mov     r9d, [r12]
0x180023962  mov     r8d, [r15]
0x180023965  mov     dword ptr [rsp+0A8h+var_88], eax
0x180023969  call    UnattendLogW
0x18002396e  mov     r14d, ebx
0x180023971  jmp     short loc_180023995
0x180023973  lea     rdx, aDismgetimagein_0; "DismGetImageInfo() failed. Error: 0x%x"
0x18002397a  mov     ecx, ebx
0x18002397c  jmp     loc_1800238D4
0x180023981  mov     edi, 57h ; 'W'
0x180023986  lea     rdx, aInvalidOutputP; "Invalid output parameter"
0x18002398d  lea     ecx, [rdi-56h]
0x180023990  call    UnattendLogW
0x180023995  mov     rcx, [rsp+0A8h+var_68]
0x18002399a  test    rcx, rcx
0x18002399d  jz      short loc_1800239AE
0x18002399f  call    cs:__imp_DismDelete
0x1800239a5  mov     [rsp+0A8h+var_68], 0
0x1800239ae  test    ebx, ebx
0x1800239b0  jz      short loc_1800239D0
0x1800239b2  call    cs:__imp_DismShutdown
0x1800239b8  test    eax, eax
0x1800239ba  jns     short loc_1800239D0
0x1800239bc  mov     r8d, eax
0x1800239bf  lea     rdx, aWinregetwimver_1; "WinReGetWimVersion failed to shutdown D"...
0x1800239c6  mov     ecx, 2
0x1800239cb  call    UnattendLogW
0x1800239d0  mov     r9d, edi
0x1800239d3  lea     rdx, aExitWinregetwi; "Exit WinReGetWimVersion return value: %"...
0x1800239da  mov     r8d, r14d
0x1800239dd  xor     ecx, ecx
0x1800239df  call    UnattendLogW
0x1800239e4  call    UnattendFinalizeLog
0x1800239e9  mov     ecx, edi; dwErrCode
0x1800239eb  call    cs:__imp_SetLastError
0x1800239f1  mov     eax, r14d
0x1800239f4  mov     rcx, [rsp+0A8h+var_58]
0x1800239f9  xor     rcx, rsp; StackCookie
0x1800239fc  call    __security_check_cookie
0x180023a01  add     rsp, 68h
0x180023a05  pop     r15
0x180023a07  pop     r14
0x180023a09  pop     r13
0x180023a0b  pop     r12
0x180023a0d  pop     rdi
0x180023a0e  pop     rsi
0x180023a0f  pop     rbp
0x180023a10  pop     rbx
0x180023a11  retn
```
