# WinMain(x,x,x,x)

- ea: `0x403116`
- end: `0x403355`
- name: `_WinMain@16`
- size: `575`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x408282`

## callees

- `0x401302`
- `0x40132b`
- `0x4015dc`
- `0x401684`
- `0x4017f7`
- `0x40187b`
- `0x4019d0`
- `0x401a2d`
- `0x401a73`
- `0x402de7`
- `0x402eb5`
- `0x402f53`
- `0x403062`
- `0x403116`
- `0x403470`
- `0x403638`
- `0x403b09`
- `0x4041cd`
- `0x404212`
- `0x4042f8`
- `0x405810`
- `0x408c05`
- `0x409120`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x40313d`
- `KERNEL32!GetProcAddress` at `0x40313d`
- `KERNEL32!GetModuleHandleW` at `0x403136`
- `KERNEL32!GetModuleHandleW` at `0x403136`
- `ADVAPI32!RegCloseKey` at `0x40331c`
- `ADVAPI32!RegCloseKey` at `0x40331c`
- `ADVAPI32!RegOpenKeyExA` at `0x403301`
- `ADVAPI32!RegOpenKeyExA` at `0x403301`
- `ADVAPI32!RegDeleteValueA` at `0x403313`
- `ADVAPI32!RegDeleteValueA` at `0x403313`
- `ole32!CoInitializeEx` at `0x403281`
- `ole32!CoInitializeEx` at `0x403281`

## string_xrefs

- `0x403131`: `kernel32.dll`
- `0x40312c`: `SetDefaultDllDirectories`
- `0x4031e5`: `asyncupdate`
- `0x4032f7`: `SOFTWARE\Microsoft\EdgeUpdate`
- `0x40330b`: `WindowsUpdateAttempts`
- `0x403232`: `WUInstallTimeout`
- `0x40321d`: `WUUpdateCheckTimeout`

## pseudocode

```c
int __stdcall WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
  HMODULE ModuleHandleW; // eax
  BOOL (__stdcall *SetDefaultDllDirectories)(DWORD); // eax
  int v6; // esi
  int v7; // eax
  char v8; // bl
  int v9; // eax
  wchar_t *v10; // esi
  int v11; // edi
  char v12; // bl
  int v13; // eax
  char v14; // bh
  unsigned int v15; // edx
  HRESULT v16; // eax
  int v17; // ecx
  int v18; // eax
  HKEY phkResult; // [esp+Ch] [ebp-58h] BYREF
  _BYTE v21[44]; // [esp+10h] [ebp-54h] BYREF
  char Parameter[28]; // [esp+3Ch] [ebp-28h] BYREF
  char v23[4]; // [esp+58h] [ebp-Ch] BYREF
  wchar_t *String; // [esp+5Ch] [ebp-8h] BYREF

  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  SetDefaultDllDirectories = (BOOL (__stdcall *)(DWORD))GetProcAddress(ModuleHandleW, "SetDefaultDllDirectories");
  if ( SetDefaultDllDirectories )
    ((void (__thiscall *)(BOOL (__stdcall *)(DWORD), int))SetDefaultDllDirectories)(SetDefaultDllDirectories, 2048);
  v6 = 0;
  String = 0;
  sub_403638(lpCmdLine);
  phkResult = 0;
  v7 = sub_40132B();
  sub_403B09(v7);
  sub_401684(&phkResult, L"/%s", L"async");
  v8 = sub_4017F7(&String, &phkResult);
  sub_401302(phkResult - 4);
  if ( !v8 )
  {
    v12 = sub_40187B();
    v23[0] = v12;
    if ( v12 )
    {
      sub_402EB5();
      sub_402F53();
    }
    phkResult = 0;
    v13 = sub_40132B();
    sub_403B09(v13);
    sub_401684(&phkResult, L"/%s", L"asyncupdate");
    v14 = sub_4017F7(&String, &phkResult);
    sub_401302(phkResult - 4);
    if ( v14 )
    {
      phkResult = 0;
    }
    else
    {
      v6 = sub_4041CD(L"WUUpdateCheckTimeout");
      phkResult = (HKEY)-2147219631;
    }
    v15 = sub_4041CD(L"WUInstallTimeout");
    if ( v12 && v14 && v15 > 0xEA60 )
      v15 = 60000;
    memset(Parameter, 0, sizeof(Parameter));
    sub_404212(Parameter, v15, v6, v23[0], (int)phkResult);
    v16 = CoInitializeEx(0, 6u);
    v10 = String;
    *(_DWORD *)v23 = v16;
    if ( v16 < 0 )
      goto LABEL_17;
    if ( !(unsigned __int8)sub_4015DC(v17) )
    {
      v16 = -2147219709;
LABEL_17:
      _mm_lfence();
      v11 = sub_402DE7(v16);
LABEL_26:
      sub_403470(v23);
      sub_4042F8(Parameter);
      goto LABEL_27;
    }
    memset(v21, 0, sizeof(v21));
    sub_4019D0((int)hInstance, v10);
    v18 = sub_401A73(v21);
    v11 = v18;
    if ( v12 )
    {
      if ( v18 == -2147219187 || v14 )
      {
        v11 = 0;
        goto LABEL_23;
      }
      v11 = v18;
      if ( !v18 )
      {
LABEL_23:
        if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\EdgeUpdate", 0, 2u, &phkResult) )
        {
          RegDeleteValueA(phkResult, "WindowsUpdateAttempts");
          RegCloseKey(phkResult);
        }
      }
    }
    sub_401A2D(v21);
    goto LABEL_26;
  }
  v9 = sub_403062(&String);
  v10 = String;
  v11 = v9;
LABEL_27:
  sub_401302(v10 - 8);
  return v11;
}

```

## disassembly

```asm
0x403116  push    ebp
0x403117  mov     ebp, esp
0x403119  sub     esp, 58h
0x40311c  mov     eax, ___security_cookie
0x403121  xor     eax, ebp
0x403123  mov     [ebp+var_4], eax
0x403126  push    ebx
0x403127  push    esi
0x403128  push    edi
0x403129  mov     edi, [ebp+lpCmdLine]
0x40312c  push    offset aSetdefaultdlld; "SetDefaultDllDirectories"
0x403131  push    offset ModuleName; "kernel32.dll"
0x403136  call    ds:GetModuleHandleW
0x40313c  push    eax; hModule
0x40313d  call    ds:GetProcAddress
0x403143  mov     esi, eax
0x403145  test    esi, esi
0x403147  jz      short loc_403158
0x403149  push    800h
0x40314e  mov     ecx, esi
0x403150  call    ds:___guard_check_icall_fptr
0x403156  call    esi
0x403158  xor     esi, esi
0x40315a  lea     ecx, [ebp+String]
0x40315d  push    edi; lpMultiByteStr
0x40315e  mov     [ebp+String], esi
0x403161  call    sub_403638
0x403166  mov     [ebp+phkResult], esi
0x403169  call    sub_40132B
0x40316e  push    eax
0x40316f  lea     ecx, [ebp+phkResult]
0x403172  call    sub_403B09
0x403177  push    offset aAsync; "async"
0x40317c  mov     edi, offset aS; "/%s"
0x403181  lea     eax, [ebp+phkResult]
0x403184  push    edi
0x403185  push    eax
0x403186  call    sub_401684
0x40318b  add     esp, 0Ch
0x40318e  lea     edx, [ebp+phkResult]
0x403191  lea     ecx, [ebp+String]
0x403194  call    sub_4017F7
0x403199  mov     ecx, [ebp+phkResult]
0x40319c  mov     bl, al
0x40319e  add     ecx, 0FFFFFFF0h
0x4031a1  call    sub_401302
0x4031a6  test    bl, bl
0x4031a8  jz      short loc_4031BC
0x4031aa  lea     ecx, [ebp+String]
0x4031ad  call    sub_403062
0x4031b2  mov     esi, [ebp+String]
0x4031b5  mov     edi, eax
0x4031b7  jmp     loc_40333A
0x4031bc  call    sub_40187B
0x4031c1  mov     bl, al
0x4031c3  mov     [ebp+var_C], bl
0x4031c6  test    bl, bl
0x4031c8  jz      short loc_4031D4
0x4031ca  call    sub_402EB5
0x4031cf  call    sub_402F53
0x4031d4  mov     [ebp+phkResult], esi
0x4031d7  call    sub_40132B
0x4031dc  push    eax
0x4031dd  lea     ecx, [ebp+phkResult]
0x4031e0  call    sub_403B09
0x4031e5  push    offset aAsyncupdate; "asyncupdate"
0x4031ea  lea     eax, [ebp+phkResult]
0x4031ed  push    edi
0x4031ee  push    eax
0x4031ef  call    sub_401684
0x4031f4  add     esp, 0Ch
0x4031f7  lea     edx, [ebp+phkResult]
0x4031fa  lea     ecx, [ebp+String]
0x4031fd  call    sub_4017F7
0x403202  mov     ecx, [ebp+phkResult]
0x403205  mov     bh, al
0x403207  add     ecx, 0FFFFFFF0h
0x40320a  call    sub_401302
0x40320f  test    bh, bh
0x403211  jz      short loc_403218
0x403213  and     [ebp+phkResult], esi
0x403216  jmp     short loc_403230
0x403218  mov     edx, 41EB0h
0x40321d  mov     ecx, offset aWuupdatecheckt; "WUUpdateCheckTimeout"
0x403222  call    sub_4041CD
0x403227  mov     esi, eax
0x403229  mov     [ebp+phkResult], 80040751h
0x403230  xor     edx, edx
0x403232  mov     ecx, offset aWuinstalltimeo; "WUInstallTimeout"
0x403237  test    bl, bl
0x403239  setz    dl
0x40323c  dec     edx
0x40323d  and     edx, 0FFCDA560h
0x403243  add     edx, 36EE80h
0x403249  call    sub_4041CD
0x40324e  mov     edx, eax
0x403250  test    bl, bl
0x403252  jz      short loc_403263
0x403254  test    bh, bh
0x403256  jz      short loc_403263
0x403258  mov     eax, 0EA60h
0x40325d  cmp     edx, eax
0x40325f  jbe     short loc_403263
0x403261  mov     edx, eax
0x403263  push    7
0x403265  pop     ecx
0x403266  push    [ebp+phkResult]; int
0x403269  xor     eax, eax
0x40326b  lea     edi, [ebp+Parameter]
0x40326e  push    dword ptr [ebp+var_C]; char
0x403271  rep stosd
0x403273  push    esi; int
0x403274  push    edx; int
0x403275  lea     ecx, [ebp+Parameter]; lpParameter
0x403278  call    sub_404212
0x40327d  push    6; dwCoInit
0x40327f  push    0; pvReserved
0x403281  call    ds:CoInitializeEx
0x403287  mov     esi, [ebp+String]
0x40328a  mov     dword ptr [ebp+var_C], eax
0x40328d  test    eax, eax
0x40328f  js      short loc_4032A1
0x403291  push    ecx
0x403292  call    sub_4015DC
0x403297  pop     ecx
0x403298  test    al, al
0x40329a  jnz     short loc_4032AF
0x40329c  mov     eax, 80040703h
0x4032a1  mov     ecx, eax
0x4032a3  lfence
0x4032a6  call    sub_402DE7
0x4032ab  mov     edi, eax
0x4032ad  jmp     short loc_40332A
0x4032af  push    2Ch ; ','; Size
0x4032b1  lea     eax, [ebp+var_54]
0x4032b4  push    0; Val
0x4032b6  push    eax; void *
0x4032b7  call    _memset
0x4032bc  add     esp, 0Ch
0x4032bf  lea     ecx, [ebp+var_54]
0x4032c2  push    esi; String
0x4032c3  push    [ebp+hInstance]; int
0x4032c6  call    sub_4019D0
0x4032cb  lea     ecx, [ebp+var_54]
0x4032ce  call    sub_401A73
0x4032d3  mov     edi, eax
0x4032d5  test    bl, bl
0x4032d7  jz      short loc_403322
0x4032d9  cmp     edi, 8004090Dh
0x4032df  jnz     short loc_4032E5
0x4032e1  xor     edi, edi
0x4032e3  jmp     short loc_4032EF
0x4032e5  test    bh, bh
0x4032e7  jnz     short loc_4032E1
0x4032e9  mov     edi, eax
0x4032eb  test    eax, eax
0x4032ed  jnz     short loc_403322
0x4032ef  lea     eax, [ebp+phkResult]
0x4032f2  push    eax; phkResult
0x4032f3  push    2; samDesired
0x4032f5  push    0; ulOptions
0x4032f7  push    offset SubKey; "SOFTWARE\\Microsoft\\EdgeUpdate"
0x4032fc  push    80000002h; hKey
0x403301  call    ds:RegOpenKeyExA
0x403307  test    eax, eax
0x403309  jnz     short loc_403322
0x40330b  push    offset ValueName; "WindowsUpdateAttempts"
0x403310  push    [ebp+phkResult]; hKey
0x403313  call    ds:RegDeleteValueA
0x403319  push    [ebp+phkResult]; hKey
0x40331c  call    ds:RegCloseKey
0x403322  lea     ecx, [ebp+var_54]
0x403325  call    sub_401A2D
0x40332a  lea     ecx, [ebp+var_C]
0x40332d  call    sub_403470
0x403332  lea     ecx, [ebp+Parameter]
0x403335  call    sub_4042F8
0x40333a  lea     ecx, [esi-10h]
0x40333d  call    sub_401302
0x403342  mov     ecx, [ebp+var_4]
0x403345  mov     eax, edi
0x403347  pop     edi
0x403348  pop     esi
0x403349  xor     ecx, ebp; StackCookie
0x40334b  pop     ebx
0x40334c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x403351  leave
0x403352  retn    10h
```
