# CProcessStateManager::_ApplyDefaultColors(bool)

- ea: `0x18001340c`
- end: `0x180013547`
- name: `?_ApplyDefaultColors@CProcessStateManager@@AEAAX_N@Z`
- size: `315`
- prototype: `void __fastcall(CProcessStateManager *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014c40`

## callees

- `0x18000df10`
- `0x18001340c`
- `0x180013550`
- `0x1800144d0`
- `0x180065380`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001344d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800134cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001344d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800134cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013473`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800134fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013473`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800134fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CProcessStateManager::_ApplyDefaultColors(CProcessStateManager *this, char a2)
{
  CUserColorData *v2; // rbx
  CUserColorData **v3; // rdi
  HKEY v4; // rcx
  CUserColorData *v5; // rdi
  CUserColorData **v6; // rdi
  HKEY v7; // rcx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  if ( a2 )
  {
    v3 = (CUserColorData **)((char *)this + 224);
    if ( !*((_QWORD *)this + 28) )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\DefaultColors\\HighContrast",
              0,
              0x20019u,
              &hKey) )
        Microsoft::WRL::Details::MakeAndInitialize<CUserColorData,CUserColorData,CAutoHandle<HKEY__ *> &>(v3, &hKey);
      v4 = hKey;
      hKey = 0;
      if ( v4 )
        RegCloseKey(v4);
    }
    v5 = *v3;
    if ( v5 )
    {
LABEL_15:
      (*(void (__fastcall **)(CUserColorData *))(*(_QWORD *)v5 + 8LL))(v5);
      v2 = v5;
      CUserColorData::ApplyColorsToSystem(v5);
    }
  }
  else
  {
    v6 = (CUserColorData **)((char *)this + 216);
    if ( !*((_QWORD *)this + 27) )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Themes\\DefaultColors\\Standard",
              0,
              0x20019u,
              &hKey) )
      {
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(v6);
        Microsoft::WRL::Details::MakeAndInitialize<CUserColorData,CUserColorData,CAutoHandle<HKEY__ *> &>(v6, &hKey);
      }
      v7 = hKey;
      hKey = 0;
      if ( v7 )
        RegCloseKey(v7);
    }
    v5 = *v6;
    if ( v5 )
      goto LABEL_15;
  }
  if ( v2 )
    (*(void (__fastcall **)(CUserColorData *))(*(_QWORD *)v2 + 16LL))(v2);
}

```

## disassembly

```asm
0x18001340c  mov     r11, rsp
0x18001340f  mov     [r11+8], rbx
0x180013413  push    rdi
0x180013414  sub     rsp, 30h
0x180013418  xor     ebx, ebx
0x18001341a  test    dl, dl
0x18001341c  jz      short loc_18001349D
0x18001341e  lea     rdi, [rcx+0E0h]
0x180013425  cmp     [rdi], rbx
0x180013428  jnz     short loc_180013479
0x18001342a  mov     [r11+18h], rbx
0x18001342e  lea     rax, [r11+18h]
0x180013432  mov     [r11-18h], rax
0x180013436  mov     r9d, 20019h; samDesired
0x18001343c  xor     r8d, r8d; ulOptions
0x18001343f  lea     rdx, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180013446  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001344d  call    cs:__imp_RegOpenKeyExW
0x180013453  test    eax, eax
0x180013455  jnz     short loc_180013464
0x180013457  lea     rdx, [rsp+38h+hKey]
0x18001345c  mov     rcx, rdi
0x18001345f  call    ??$MakeAndInitialize@VCUserColorData@@V1@AEAV?$CAutoHandle@PEAUHKEY__@@@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCUserColorData@@@WRL@Microsoft@@@012@AEAV?$CAutoHandle@PEAUHKEY__@@@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CUserColorData,CUserColorData,CAutoHandle<HKEY__ *> &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CUserColorData>>,CAutoHandle<HKEY__ *> &)
0x180013464  mov     rcx, [rsp+38h+hKey]; hKey
0x180013469  mov     [rsp+38h+hKey], rbx
0x18001346e  test    rcx, rcx
0x180013471  jz      short loc_180013479
0x180013473  call    cs:__imp_RegCloseKey
0x180013479  mov     rdi, [rdi]
0x18001347c  test    rdi, rdi
0x18001347f  jz      loc_180013527
0x180013485  mov     rax, [rdi]
0x180013488  mov     rcx, rdi
0x18001348b  mov     rax, [rax+8]
0x18001348f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013494  nop
0x180013495  mov     rbx, rdi
0x180013498  jmp     loc_18001351E
0x18001349d  lea     rdi, [rcx+0D8h]
0x1800134a4  cmp     [rdi], rbx
0x1800134a7  jnz     short loc_180013503
0x1800134a9  mov     [rsp+38h+hKey], rbx
0x1800134ae  lea     rax, [rsp+38h+hKey]
0x1800134b3  mov     [rsp+38h+phkResult], rax; phkResult
0x1800134b8  mov     r9d, 20019h; samDesired
0x1800134be  xor     r8d, r8d; ulOptions
0x1800134c1  lea     rdx, aSoftwareMicros_14; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800134c8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800134cf  call    cs:__imp_RegOpenKeyExW
0x1800134d5  test    eax, eax
0x1800134d7  jnz     short loc_1800134EE
0x1800134d9  mov     rcx, rdi
0x1800134dc  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800134e1  lea     rdx, [rsp+38h+hKey]
0x1800134e6  mov     rcx, rdi
0x1800134e9  call    ??$MakeAndInitialize@VCUserColorData@@V1@AEAV?$CAutoHandle@PEAUHKEY__@@@@@Details@WRL@Microsoft@@YAJPEAPEAVCUserColorData@@AEAV?$CAutoHandle@PEAUHKEY__@@@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CUserColorData,CUserColorData,CAutoHandle<HKEY__ *> &>(CUserColorData * *,CAutoHandle<HKEY__ *> &)
0x1800134ee  mov     rcx, [rsp+38h+hKey]; hKey
0x1800134f3  mov     [rsp+38h+hKey], rbx
0x1800134f8  test    rcx, rcx
0x1800134fb  jz      short loc_180013503
0x1800134fd  call    cs:__imp_RegCloseKey
0x180013503  mov     rdi, [rdi]
0x180013506  test    rdi, rdi
0x180013509  jz      short loc_180013527
0x18001350b  mov     rax, [rdi]
0x18001350e  mov     rcx, rdi
0x180013511  mov     rax, [rax+8]
0x180013515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001351a  nop
0x18001351b  mov     rbx, rdi
0x18001351e  mov     rcx, rbx; this
0x180013521  call    ?ApplyColorsToSystem@CUserColorData@@QEAAHXZ; CUserColorData::ApplyColorsToSystem(void)
0x180013526  nop
0x180013527  test    rbx, rbx
0x18001352a  jz      short loc_18001353C
0x18001352c  mov     rax, [rbx]
0x18001352f  mov     rcx, rbx
0x180013532  mov     rax, [rax+10h]
0x180013536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001353b  nop
0x18001353c  mov     rbx, [rsp+38h+arg_0]
0x180013541  add     rsp, 30h
0x180013545  pop     rdi
0x180013546  retn
```
