# SepRouterHookEat

- ea: `0x180039170`
- end: `0x180039395`
- name: `SepRouterHookEat`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18001fca0`

## callees

- `0x18000f114`
- `0x180010fb0`
- `0x180020a68`
- `0x180027380`
- `0x1800373bc`
- `0x180039170`

## import_xrefs

- `ntdll!RtlImageDirectoryEntryToData` at `0x1800391b9`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800391b9`
- `ntdll!NtProtectVirtualMemory` at `0x180039282`
- `ntdll!NtProtectVirtualMemory` at `0x180039282`

## pseudocode

```c
__int64 __fastcall SepRouterHookEat(__int64 a1, __int64 a2)
{
  void *v3; // rcx
  PVOID v5; // rax
  __int64 v6; // rdx
  int v7; // edi
  NTSTATUS v8; // eax
  __int64 i; // rdi
  unsigned __int64 v11; // rsi
  __int64 v12; // r14
  __int64 v13; // r15
  unsigned __int64 v14; // rcx
  __int128 v15; // [rsp+30h] [rbp-20h] BYREF
  ULONG NewAccessProtection[4]; // [rsp+40h] [rbp-10h] BYREF
  SIZE_T Size; // [rsp+80h] [rbp+30h] BYREF
  PVOID BaseAddress; // [rsp+88h] [rbp+38h] BYREF

  LODWORD(BaseAddress) = 0;
  LODWORD(Size) = 0;
  v3 = *(void **)(a2 + 48);
  v15 = (unsigned __int64)v3;
  *(_OWORD *)NewAccessProtection = 0;
  v5 = RtlImageDirectoryEntryToData(v3, 1u, 0, (PULONG)&Size);
  v6 = *(_QWORD *)(a1 + 16);
  *((_QWORD *)&v15 + 1) = v5;
  *(_QWORD *)NewAccessProtection = (unsigned int)Size;
  LODWORD(Size) = 0;
  v7 = SeModuleTrackerModuleLoaded(&Size, v6, 0, a2);
  if ( v7 >= 0 )
  {
    if ( (unsigned int)SeRouterCanHookModule(a2, (unsigned int)Size) )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v11 = *(_QWORD *)(a2 + 48);
        v12 = *((_QWORD *)&v15 + 1);
        v13 = *(unsigned int *)(a2 + 64);
        if ( (unsigned __int8)LUIsCorIlOnlyImage(v11) || !v12 || (unsigned int)i >= *(_DWORD *)(v12 + 20) )
          break;
        v14 = v11 + *(unsigned int *)(v12 + 28);
        if ( v14 < v11 )
        {
          AslLogCallPrintf(1, "SepRouterHookEat", 1418, "EnumExportedFunctionsInModule failed [%d]", 534);
          v7 = -1073741595;
          goto LABEL_6;
        }
        if ( v14 > v11 + v13 )
          break;
        if ( (int)SepRouterHookExportedApi((unsigned int)&BaseAddress, a1, (unsigned int)&v15, a2, v14 + 8 * i) < 0 )
          AslLogCallPrintf(
            1,
            "SepRouterHookEat",
            1434,
            "Failed to hook API # %ld in %S",
            i,
            *(const wchar_t **)(a2 + 96));
      }
    }
    else
    {
      AslLogCallPrintf(3, "SepRouterHookEat", 1401, "Excluding %S from hooking", *(const wchar_t **)(a2 + 96));
    }
    v7 = 0;
  }
  else
  {
    AslLogCallPrintf(
      1,
      "SepRouterHookEat",
      1392,
      "Failed to get %S from the Module Tracker",
      *(const wchar_t **)(a2 + 96));
  }
LABEL_6:
  BaseAddress = (PVOID)*((_QWORD *)&v15 + 1);
  Size = *(_QWORD *)NewAccessProtection;
  if ( *((_QWORD *)&v15 + 1) )
  {
    if ( NewAccessProtection[2] )
    {
      v8 = NtProtectVirtualMemory(
             (HANDLE)0xFFFFFFFFFFFFFFFFLL,
             &BaseAddress,
             &Size,
             NewAccessProtection[2],
             &NewAccessProtection[2]);
      if ( v8 < 0 )
        AslLogCallPrintf(1, "SepEatStateReset", 448, "Failed to restore EAT protection: %08lx", v8);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180039170  mov     [rsp-28h+arg_10], rbx
0x180039175  mov     [rsp-28h+arg_18], rsi
0x18003917a  push    rbp
0x18003917b  push    rdi
0x18003917c  push    r13
0x18003917e  push    r14
0x180039180  push    r15
0x180039182  mov     rbp, rsp
0x180039185  sub     rsp, 50h
0x180039189  xorps   xmm0, xmm0
0x18003918c  mov     dword ptr [rbp+BaseAddress], 0
0x180039193  mov     r13, rcx
0x180039196  mov     dword ptr [rbp+Size], 0
0x18003919d  mov     rcx, [rdx+30h]; BaseAddress
0x1800391a1  lea     r9, [rbp+Size]; Size
0x1800391a5  mov     rbx, rdx
0x1800391a8  xor     r8d, r8d; Directory
0x1800391ab  movups  [rbp+var_20], xmm0
0x1800391af  mov     dl, 1; MappedAsImage
0x1800391b1  mov     qword ptr [rbp+var_20], rcx
0x1800391b5  movups  xmmword ptr [rbp+NewAccessProtection], xmm0
0x1800391b9  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800391bf  mov     rdx, [r13+10h]
0x1800391c3  lea     rcx, [rbp+Size]
0x1800391c7  mov     qword ptr [rbp+var_20+8], rax
0x1800391cb  mov     r9, rbx
0x1800391ce  mov     eax, dword ptr [rbp+Size]
0x1800391d1  xor     r8d, r8d
0x1800391d4  mov     qword ptr [rbp+NewAccessProtection], rax
0x1800391d8  mov     dword ptr [rbp+Size], 0
0x1800391df  call    SeModuleTrackerModuleLoaded
0x1800391e4  mov     edi, eax
0x1800391e6  test    eax, eax
0x1800391e8  jns     short loc_180039213
0x1800391ea  mov     rcx, [rbx+60h]
0x1800391ee  lea     r9, aFailedToGetSFr; "Failed to get %S from the Module Tracke"...
0x1800391f5  mov     [rsp+50h+OldAccessProtection], rcx
0x1800391fa  lea     rdx, aSeprouterhooke_0; "SepRouterHookEat"
0x180039201  mov     ecx, 1
0x180039206  mov     r8d, 570h
0x18003920c  call    AslLogCallPrintf
0x180039211  jmp     short loc_18003924F
0x180039213  mov     edx, dword ptr [rbp+Size]
0x180039216  mov     rcx, rbx
0x180039219  call    SeRouterCanHookModule
0x18003921e  test    eax, eax
0x180039220  jnz     loc_1800392C9
0x180039226  mov     rax, [rbx+60h]
0x18003922a  lea     r9, aExcludingSFrom_0; "Excluding %S from hooking"
0x180039231  mov     r8d, 579h
0x180039237  mov     [rsp+50h+OldAccessProtection], rax
0x18003923c  lea     rdx, aSeprouterhooke_0; "SepRouterHookEat"
0x180039243  mov     ecx, 3
0x180039248  call    AslLogCallPrintf
0x18003924d  xor     edi, edi
0x18003924f  mov     rcx, qword ptr [rbp+var_20+8]
0x180039253  mov     rax, qword ptr [rbp+NewAccessProtection]
0x180039257  mov     [rbp+BaseAddress], rcx
0x18003925b  mov     [rbp+Size], rax
0x18003925f  test    rcx, rcx
0x180039262  jz      short loc_1800392AE
0x180039264  mov     r9, qword ptr [rbp+NewAccessProtection+8]; NewAccessProtection
0x180039268  test    r9d, r9d
0x18003926b  jz      short loc_1800392AE
0x18003926d  lea     rax, [rbp+NewAccessProtection+8]
0x180039271  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180039275  lea     r8, [rbp+Size]; NumberOfBytesToProtect
0x180039279  mov     [rsp+50h+OldAccessProtection], rax; OldAccessProtection
0x18003927e  lea     rdx, [rbp+BaseAddress]; BaseAddress
0x180039282  call    cs:__imp_NtProtectVirtualMemory
0x180039288  test    eax, eax
0x18003928a  jns     short loc_1800392AE
0x18003928c  lea     r9, aFailedToRestor_0; "Failed to restore EAT protection: %08lx"
0x180039293  mov     dword ptr [rsp+50h+OldAccessProtection], eax
0x180039297  mov     r8d, 1C0h
0x18003929d  lea     rdx, aSepeatstateres; "SepEatStateReset"
0x1800392a4  mov     ecx, 1
0x1800392a9  call    AslLogCallPrintf
0x1800392ae  lea     r11, [rsp+50h+var_s0]
0x1800392b3  mov     eax, edi
0x1800392b5  mov     rbx, [r11+40h]
0x1800392b9  mov     rsi, [r11+48h]
0x1800392bd  mov     rsp, r11
0x1800392c0  pop     r15
0x1800392c2  pop     r14
0x1800392c4  pop     r13
0x1800392c6  pop     rdi
0x1800392c7  pop     rbp
0x1800392c8  retn
0x1800392c9  xor     edi, edi
0x1800392cb  mov     rsi, [rbx+30h]
0x1800392cf  mov     r14, qword ptr [rbp+var_20+8]
0x1800392d3  mov     rcx, rsi
0x1800392d6  mov     r15d, [rbx+40h]
0x1800392da  call    LUIsCorIlOnlyImage
0x1800392df  test    al, al
0x1800392e1  jnz     loc_18003924D
0x1800392e7  test    r14, r14
0x1800392ea  jz      loc_18003924D
0x1800392f0  cmp     edi, [r14+14h]
0x1800392f4  jnb     loc_18003924D
0x1800392fa  mov     ecx, [r14+1Ch]
0x1800392fe  add     rcx, rsi
0x180039301  cmp     rcx, rsi
0x180039304  jb      short loc_180039365
0x180039306  lea     rax, [rsi+r15]
0x18003930a  cmp     rcx, rax
0x18003930d  ja      loc_18003924D
0x180039313  lea     rcx, [rcx+rdi*8]
0x180039317  mov     r9, rbx
0x18003931a  mov     [rsp+50h+OldAccessProtection], rcx
0x18003931f  lea     r8, [rbp+var_20]
0x180039323  lea     rcx, [rbp+BaseAddress]
0x180039327  mov     rdx, r13
0x18003932a  call    SepRouterHookExportedApi
0x18003932f  test    eax, eax
0x180039331  jns     short loc_18003935E
0x180039333  mov     rax, [rbx+60h]
0x180039337  lea     r9, aFailedToHookAp; "Failed to hook API # %ld in %S"
0x18003933e  mov     [rsp+50h+var_28], rax
0x180039343  lea     rdx, aSeprouterhooke_0; "SepRouterHookEat"
0x18003934a  mov     r8d, 59Ah
0x180039350  mov     dword ptr [rsp+50h+OldAccessProtection], edi
0x180039354  mov     ecx, 1
0x180039359  call    AslLogCallPrintf
0x18003935e  inc     edi
0x180039360  jmp     loc_1800392CB
0x180039365  lea     r9, aEnumexportedfu; "EnumExportedFunctionsInModule failed [%"...
0x18003936c  mov     dword ptr [rsp+50h+OldAccessProtection], 216h
0x180039374  mov     r8d, 58Ah
0x18003937a  lea     rdx, aSeprouterhooke_0; "SepRouterHookEat"
0x180039381  mov     ecx, 1
0x180039386  call    AslLogCallPrintf
0x18003938b  mov     edi, 0C00000E5h
0x180039390  jmp     loc_18003924F
```
