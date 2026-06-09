# RestoreLockWorkstation(HKEY__ *,ushort const *,ushort const *)

- ea: `0x140074678`
- end: `0x140074904`
- name: `?RestoreLockWorkstation@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `652`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001edf0`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140074678`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1400746dd`
- `ADVAPI32!RegGetValueW` at `0x1400747d9`
- `ADVAPI32!RegGetValueW` at `0x1400746dd`
- `ADVAPI32!RegGetValueW` at `0x1400747d9`
- `ADVAPI32!RegDeleteKeyValueW` at `0x14007477f`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140074815`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140074843`
- `ADVAPI32!RegDeleteKeyValueW` at `0x14007477f`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140074815`
- `ADVAPI32!RegDeleteKeyValueW` at `0x140074843`
- `ADVAPI32!RegSetKeyValueW` at `0x140074750`
- `ADVAPI32!RegSetKeyValueW` at `0x140074750`
- `KERNEL32!IsDebuggerPresent` at `0x14007489c`
- `KERNEL32!IsDebuggerPresent` at `0x14007489c`

## string_xrefs

- `0x1400747b5`: `DisableLockWorkstation.WMS.DeletePolicyOnRestore`
- `0x140074836`: `DisableLockWorkstation.WMS.DeletePolicyOnRestore`
- `0x140074884`: `termsrv\wms\src\common\srcutils\lockworkstation.cpp`

## pseudocode

```c
__int64 __fastcall RestoreLockWorkstation(HKEY hKey, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  LSTATUS ValueW; // eax
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // r14
  unsigned int v7; // r13d
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  LPDWORD pcbData; // [rsp+30h] [rbp-48h]
  unsigned int v15; // [rsp+38h] [rbp-40h]
  DWORD v16; // [rsp+88h] [rbp+10h] BYREF
  int v17; // [rsp+8Ch] [rbp+14h]
  unsigned int Data; // [rsp+90h] [rbp+18h] BYREF
  int v19; // [rsp+94h] [rbp+1Ch]
  int pvData; // [rsp+98h] [rbp+20h] BYREF

  v19 = HIDWORD(a3);
  v17 = HIDWORD(a2);
  Data = 0;
  pvData = 0;
  v16 = 4;
  ValueW = RegGetValueW(
             hKey,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
             L"DisableLockWorkstation.WMS.bak",
             0x10u,
             0,
             &Data,
             &v16);
  v5 = ValueW;
  if ( !ValueW )
  {
    DEBUGMSG(
      L"RestoreLockWorkstation - restoring original policy setting of %s = %d\n",
      L"DisableLockWorkstation",
      Data);
    v8 = RegSetKeyValueW(
           hKey,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
           L"DisableLockWorkstation",
           4u,
           &Data,
           4u);
    v5 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
      v7 = 125;
    }
    else
    {
      v9 = RegDeleteKeyValueW(
             hKey,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
             L"DisableLockWorkstation.WMS.bak");
      v5 = v9;
      if ( !v9 )
        goto LABEL_14;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      v7 = 128;
    }
LABEL_30:
    v6 = L"err == 0L";
    goto LABEL_31;
  }
  if ( ValueW != 2 )
  {
    if ( ValueW > 0 )
      v5 = (unsigned __int16)ValueW | 0x80070000;
    v6 = L"err == 2L";
    v7 = 116;
    goto LABEL_31;
  }
LABEL_14:
  v16 = 4;
  v5 = 0;
  v10 = RegGetValueW(
          hKey,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
          L"DisableLockWorkstation.WMS.DeletePolicyOnRestore",
          0x10u,
          0,
          &pvData,
          &v16);
  if ( !v10 )
  {
    v11 = RegDeleteKeyValueW(
            hKey,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
            L"DisableLockWorkstation");
    if ( v11 )
    {
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      else
        v5 = v11;
      v7 = 147;
    }
    else
    {
      v12 = RegDeleteKeyValueW(
              hKey,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
              L"DisableLockWorkstation.WMS.DeletePolicyOnRestore");
      if ( !v12 )
        return v5;
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
      else
        v5 = v12;
      v7 = 150;
    }
    goto LABEL_30;
  }
  if ( v10 == 2 )
    return v5;
  if ( v10 > 0 )
    v5 = (unsigned __int16)v10 | 0x80070000;
  else
    v5 = v10;
  v6 = L"err == 2L";
  v7 = 142;
LABEL_31:
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\lockworkstation.cpp",
    v7,
    L"RestoreLockWorkstation",
    L"CBRAEx",
    v6,
    v5);
  if ( IsDebuggerPresent() )
  {
    v15 = v5;
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\lockworkstation.cpp",
      v7,
      L"RestoreLockWorkstation",
      L"CBRAEx",
      v6,
      v15);
  }
  else
  {
    LODWORD(pcbData) = v5;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\lockworkstation.cpp",
      v7,
      L"RestoreLockWorkstation",
      L"CBRAEx",
      v6,
      pcbData);
  }
  return v5;
}

```

## disassembly

```asm
0x140074678  mov     r11, rsp
0x14007467b  mov     [r11+18h], r8
0x14007467f  mov     [r11+10h], rdx
0x140074683  push    rbx
0x140074684  push    rbp
0x140074685  push    rsi
0x140074686  push    rdi
0x140074687  push    r12
0x140074689  push    r13
0x14007468b  push    r14
0x14007468d  sub     rsp, 40h
0x140074691  lea     rax, [r11+10h]
0x140074695  mov     dword ptr [r11+18h], 0
0x14007469d  mov     [r11-48h], rax
0x1400746a1  lea     rsi, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400746a8  mov     ebp, 4
0x1400746ad  mov     dword ptr [r11+20h], 0
0x1400746b5  lea     rax, [r11+18h]
0x1400746b9  mov     [r11+10h], ebp
0x1400746bd  mov     [r11-50h], rax
0x1400746c1  lea     r8, aDisablelockwor; "DisableLockWorkstation.WMS.bak"
0x1400746c8  mov     rdx, rsi; lpSubKey
0x1400746cb  mov     qword ptr [r11-58h], 0
0x1400746d3  lea     r13d, [rbp+0Ch]
0x1400746d7  mov     rdi, rcx
0x1400746da  mov     r9d, r13d; dwFlags
0x1400746dd  call    cs:__imp_RegGetValueW
0x1400746e3  lea     r12d, [rbp-2]
0x1400746e7  mov     ebx, eax
0x1400746e9  lea     r14, aDisablelockwor_1; "DisableLockWorkstation"
0x1400746f0  test    eax, eax
0x1400746f2  jz      short loc_14007471C
0x1400746f4  cmp     eax, r12d
0x1400746f7  jz      loc_1400747A1
0x1400746fd  test    eax, eax
0x1400746ff  jle     short loc_14007470A
0x140074701  movzx   ebx, ax
0x140074704  or      ebx, 80070000h
0x14007470a  lea     r14, aErr2l; "err == 2L"
0x140074711  mov     r13d, 74h ; 't'
0x140074717  jmp     loc_14007486D
0x14007471c  mov     r8d, [rsp+78h+Data]
0x140074724  lea     rcx, aRestorelockwor; "RestoreLockWorkstation - restoring orig"...
0x14007472b  mov     rdx, r14
0x14007472e  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140074733  lea     rax, [rsp+78h+Data]
0x14007473b  mov     [rsp+78h+cbData], ebp; cbData
0x14007473f  mov     r9d, ebp; dwType
0x140074742  mov     [rsp+78h+lpData], rax; lpData
0x140074747  mov     r8, r14; lpValueName
0x14007474a  mov     rdx, rsi; lpSubKey
0x14007474d  mov     rcx, rdi; hKey
0x140074750  call    cs:__imp_RegSetKeyValueW
0x140074756  mov     ebx, eax
0x140074758  test    eax, eax
0x14007475a  jz      short loc_140074772
0x14007475c  jle     short loc_140074767
0x14007475e  movzx   ebx, ax
0x140074761  or      ebx, 80070000h
0x140074767  mov     r13d, 7Dh ; '}'
0x14007476d  jmp     loc_140074866
0x140074772  lea     r8, aDisablelockwor; "DisableLockWorkstation.WMS.bak"
0x140074779  mov     rdx, rsi; lpSubKey
0x14007477c  mov     rcx, rdi; hKey
0x14007477f  call    cs:__imp_RegDeleteKeyValueW
0x140074785  mov     ebx, eax
0x140074787  test    eax, eax
0x140074789  jz      short loc_1400747A1
0x14007478b  jle     short loc_140074796
0x14007478d  movzx   ebx, ax
0x140074790  or      ebx, 80070000h
0x140074796  mov     r13d, 80h
0x14007479c  jmp     loc_140074866
0x1400747a1  lea     rax, [rsp+78h+arg_8]
0x1400747a9  mov     [rsp+78h+arg_8], ebp
0x1400747b0  mov     [rsp+78h+pcbData], rax; pcbData
0x1400747b5  lea     r8, aDisablelockwor_0; "DisableLockWorkstation.WMS.DeletePolicy"...
0x1400747bc  lea     rax, [rsp+78h+pvData]
0x1400747c4  xor     ebx, ebx
0x1400747c6  mov     qword ptr [rsp+78h+cbData], rax; pvData
0x1400747cb  mov     r9d, r13d; dwFlags
0x1400747ce  mov     rdx, rsi; lpSubKey
0x1400747d1  mov     [rsp+78h+lpData], rbx; pdwType
0x1400747d6  mov     rcx, rdi; hkey
0x1400747d9  call    cs:__imp_RegGetValueW
0x1400747df  test    eax, eax
0x1400747e1  jz      short loc_14007480C
0x1400747e3  cmp     eax, r12d
0x1400747e6  jz      loc_1400748F3
0x1400747ec  test    eax, eax
0x1400747ee  jg      short loc_1400747F4
0x1400747f0  mov     ebx, eax
0x1400747f2  jmp     short loc_1400747FD
0x1400747f4  movzx   ebx, ax
0x1400747f7  or      ebx, 80070000h
0x1400747fd  lea     r14, aErr2l; "err == 2L"
0x140074804  mov     r13d, 8Eh
0x14007480a  jmp     short loc_14007486D
0x14007480c  mov     r8, r14; lpValueName
0x14007480f  mov     rdx, rsi; lpSubKey
0x140074812  mov     rcx, rdi; hKey
0x140074815  call    cs:__imp_RegDeleteKeyValueW
0x14007481b  test    eax, eax
0x14007481d  jz      short loc_140074836
0x14007481f  jg      short loc_140074825
0x140074821  mov     ebx, eax
0x140074823  jmp     short loc_14007482E
0x140074825  movzx   ebx, ax
0x140074828  or      ebx, 80070000h
0x14007482e  mov     r13d, 93h
0x140074834  jmp     short loc_140074866
0x140074836  lea     r8, aDisablelockwor_0; "DisableLockWorkstation.WMS.DeletePolicy"...
0x14007483d  mov     rdx, rsi; lpSubKey
0x140074840  mov     rcx, rdi; hKey
0x140074843  call    cs:__imp_RegDeleteKeyValueW
0x140074849  test    eax, eax
0x14007484b  jz      loc_1400748F3
0x140074851  jg      short loc_140074857
0x140074853  mov     ebx, eax
0x140074855  jmp     short loc_140074860
0x140074857  movzx   ebx, ax
0x14007485a  or      ebx, 80070000h
0x140074860  mov     r13d, 96h
0x140074866  lea     r14, aErr0l; "err == 0L"
0x14007486d  lea     rbp, aCbraex; "CBRAEx"
0x140074874  mov     [rsp+78h+cbData], ebx; int
0x140074878  lea     rsi, aRestorelockwor_0; "RestoreLockWorkstation"
0x14007487f  mov     [rsp+78h+lpData], r14; unsigned __int16 *
0x140074884  lea     rdi, aTermsrvWmsSrcC_28; "termsrv\\wms\\src\\common\\srcutils\\lo"...
0x14007488b  mov     r9, rbp; unsigned __int16 *
0x14007488e  mov     r8, rsi; unsigned __int16 *
0x140074891  mov     rcx, rdi; unsigned __int16 *
0x140074894  mov     edx, r13d; unsigned int
0x140074897  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007489c  call    cs:__imp_IsDebuggerPresent
0x1400748a2  test    eax, eax
0x1400748a4  jz      short loc_1400748D0
0x1400748a6  mov     [rsp+78h+var_40], ebx
0x1400748aa  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400748b1  mov     [rsp+78h+pcbData], r14
0x1400748b6  mov     r9d, r13d
0x1400748b9  mov     qword ptr [rsp+78h+cbData], rbp
0x1400748be  mov     r8, rdi
0x1400748c1  mov     ecx, r12d; unsigned __int8
0x1400748c4  mov     [rsp+78h+lpData], rsi
0x1400748c9  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400748ce  jmp     short loc_1400748F3
0x1400748d0  mov     dword ptr [rsp+78h+pcbData], ebx
0x1400748d4  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400748db  mov     qword ptr [rsp+78h+cbData], r14
0x1400748e0  mov     r9, rsi
0x1400748e3  mov     r8d, r13d
0x1400748e6  mov     [rsp+78h+lpData], rbp
0x1400748eb  mov     rdx, rdi
0x1400748ee  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400748f3  mov     eax, ebx
0x1400748f5  add     rsp, 40h
0x1400748f9  pop     r14
0x1400748fb  pop     r13
0x1400748fd  pop     r12
0x1400748ff  pop     rdi
0x140074900  pop     rsi
0x140074901  pop     rbp
0x140074902  pop     rbx
0x140074903  retn
```
