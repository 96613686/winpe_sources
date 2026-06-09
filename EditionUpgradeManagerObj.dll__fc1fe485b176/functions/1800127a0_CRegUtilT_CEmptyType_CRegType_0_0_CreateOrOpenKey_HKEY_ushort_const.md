# CRegUtilT<CEmptyType,CRegType,0,0>::CreateOrOpenKey(HKEY__ *,ushort const *)

- ea: `0x1800127a0`
- end: `0x1800128bb`
- name: `?CreateOrOpenKey@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800156d0`
- `0x180015864`
- `0x1800161b0`
- `0x180016320`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x1800127a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012850`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012893`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012850`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012893`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012803`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012803`

## pseudocode

```c
__int64 __fastcall CRegUtilT<CEmptyType,CRegType,0,0>::CreateOrOpenKey(__int64 a1, const WCHAR *a2)
{
  int v2; // eax
  HKEY v3; // rbx
  int v4; // edi
  DWORD v6; // [rsp+80h] [rbp+8h] BYREF
  int v7; // [rsp+84h] [rbp+Ch]
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  v7 = HIDWORD(a1);
  v6 = 0;
  hKey = 0;
  v2 = RegCreateKeyExW(HKEY_CLASSES_ROOT, a2, 0, 0, 0, 0x20019u, 0, &hKey, &v6);
  if ( v2 )
  {
    v3 = 0;
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    v4 = v2;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v2);
  }
  else
  {
    v3 = hKey;
    v4 = 0;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 < 0 )
    goto LABEL_9;
  if ( v6 == 1 )
  {
    v4 = 0;
  }
  else
  {
    if ( v6 != 2 )
    {
      v4 = -2147418113;
LABEL_9:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
      goto LABEL_15;
    }
    v4 = 1;
  }
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( v3 )
    RegCloseKey(v3);
  if ( v4 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800127a0  mov     r11, rsp
0x1800127a3  mov     [r11+10h], rbx
0x1800127a7  mov     [r11+8], rcx
0x1800127ab  push    rdi
0x1800127ac  sub     rsp, 70h
0x1800127b0  xor     eax, eax
0x1800127b2  mov     dword ptr [r11+8], 0
0x1800127ba  xorps   xmm0, xmm0
0x1800127bd  mov     qword ptr [r11+18h], 0
0x1800127c5  movups  [rsp+78h+var_28], xmm0
0x1800127ca  mov     [r11-18h], rax
0x1800127ce  xor     r9d, r9d; lpClass
0x1800127d1  lea     rax, [r11+8]
0x1800127d5  xor     r8d, r8d; Reserved
0x1800127d8  mov     [r11-38h], rax
0x1800127dc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800127e3  lea     rax, [r11+18h]
0x1800127e7  mov     [r11-40h], rax
0x1800127eb  mov     qword ptr [r11-48h], 0
0x1800127f3  mov     [rsp+78h+samDesired], 20019h; samDesired
0x1800127fb  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180012803  call    cs:__imp_RegCreateKeyExW
0x180012809  test    eax, eax
0x18001280b  jz      short loc_180012826
0x18001280d  xor     ebx, ebx
0x18001280f  test    eax, eax
0x180012811  jle     short loc_18001281B
0x180012813  movzx   eax, ax
0x180012816  or      eax, 80070000h
0x18001281b  mov     ecx, eax
0x18001281d  mov     edi, eax
0x18001281f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012824  jmp     short loc_18001283C
0x180012826  mov     rbx, [rsp+78h+hKey]
0x18001282e  xor     edi, edi
0x180012830  mov     [rsp+78h+hKey], 0
0x18001283c  mov     ecx, edi
0x18001283e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012843  mov     rcx, [rsp+78h+hKey]; hKey
0x18001284b  test    rcx, rcx
0x18001284e  jz      short loc_180012856
0x180012850  call    cs:__imp_RegCloseKey
0x180012856  test    edi, edi
0x180012858  jns     short loc_180012863
0x18001285a  mov     ecx, edi
0x18001285c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012861  jmp     short loc_180012884
0x180012863  mov     eax, [rsp+78h+arg_0]
0x18001286a  sub     eax, 1
0x18001286d  jz      short loc_180012882
0x18001286f  cmp     eax, 1
0x180012872  jz      short loc_18001287B
0x180012874  mov     edi, 8000FFFFh
0x180012879  jmp     short loc_18001285A
0x18001287b  mov     edi, 1
0x180012880  jmp     short loc_180012884
0x180012882  xor     edi, edi
0x180012884  mov     ecx, edi
0x180012886  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001288b  test    rbx, rbx
0x18001288e  jz      short loc_180012899
0x180012890  mov     rcx, rbx; hKey
0x180012893  call    cs:__imp_RegCloseKey
0x180012899  test    edi, edi
0x18001289b  jns     short loc_1800128A4
0x18001289d  mov     ecx, edi
0x18001289f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800128a4  mov     ecx, edi
0x1800128a6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800128ab  mov     rbx, [rsp+78h+arg_8]
0x1800128b3  mov     eax, edi
0x1800128b5  add     rsp, 70h
0x1800128b9  pop     rdi
0x1800128ba  retn
```
