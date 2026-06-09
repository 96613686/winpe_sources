# AhcInitialize

- ea: `0x14002a3dc`
- end: `0x14002a6ae`
- name: `AhcInitialize`
- size: `722`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002c990`

## callees

- `0x1400012f0`
- `0x140025054`
- `0x1400260f8`
- `0x1400279dc`
- `0x140027af4`
- `0x140029020`
- `0x140029320`
- `0x1400293c4`
- `0x14002a3dc`
- `0x14002ad30`
- `0x14002ade8`
- `0x14002bb4c`
- `0x14002bd74`
- `0x14003e364`
- `0x140054c34`

## import_xrefs

- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14002a4df`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14002a4df`

## string_xrefs

- `0x14002a509`: `RtlStringCchCopyW failed [%x]`
- `0x14002a4c2`: `AppCompatCache`
- `0x14002a475`: `Failed to create cache object [%x]`
- `0x14002a4b4`: `\Registry\MACHINE\System\CurrentControlSet\Control\Session Manager\AppCompatCache`
- `0x14002a4ef`: `\Registry\MACHINE\System\CurrentControlSet\Control\Session Manager\AppCompatCache`
- `0x14002a526`: `Ahc reg path: %ws`
- `0x14002a54a`: `Failed to initialize cache [%x]`
- `0x14002a576`: `Failed to clear cache apphelp data [%x]`
- `0x14002a5b3`: `Failed to create cdb object [%x]`
- `0x14002a5f1`: `Failed to create SdbQuery object [%x]`

## pseudocode

```c
__int64 __fastcall AhcInitialize(__int64 a1)
{
  int v2; // edi
  __int64 v3; // rdx
  int v4; // eax
  const char *v5; // r9
  __int64 v6; // r8
  int Registry; // eax
  int v8; // eax
  void *v9; // rdx
  __int64 v10; // r8
  const char *v11; // r9
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-48h]

  if ( !*(_DWORD *)(a1 + 704) )
    g_AslLogPfnVPrintf = (__int64)&AhcLogVPrintf;
  AslLogCallPrintf(3, "AhcInitialize", 71, "Enter.");
  v2 = AhcLockCreate(a1 + 16);
  if ( v2 < 0 || !*(_QWORD *)(a1 + 16) )
  {
    v10 = 75;
    v11 = "Failed to initialize quirks table lock";
LABEL_26:
    AslLogCallPrintf(1, "AhcInitialize", v10, v11);
    if ( v2 >= 0 )
      return (unsigned int)v2;
    goto LABEL_27;
  }
  v2 = AhcLockCreate(a1 + 720);
  if ( v2 < 0 || !*(_QWORD *)(a1 + 720) )
  {
    v10 = 81;
    v11 = "Failed to initialize shared sdb handle lock";
    goto LABEL_26;
  }
  v4 = AhcCacheCreate((__int64 *)(a1 + 24), v3, a1 + 72);
  v2 = v4;
  if ( v4 >= 0 )
  {
    *(_OWORD *)(a1 + 40) = 0;
    *(_OWORD *)(a1 + 56) = 0;
    *(_OWORD *)(a1 + 72) = 0;
    *(_DWORD *)(a1 + 88) = 0;
    *(_DWORD *)(a1 + 40) = 52;
    if ( (int)RtlGetPersistedStateLocation(
                L"AppCompatCache",
                0,
                L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Session Manager\\AppCompatCache",
                0,
                a1 + 128,
                520,
                0) >= 0
      || (v4 = RtlStringCchCopyW(
                 (NTSTRSAFE_PWSTR)(a1 + 128),
                 0x104u,
                 L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Session Manager\\AppCompatCache"),
          v2 = v4,
          v4 >= 0) )
    {
      AslLogCallPrintf(3, "AhcInitialize", 123, "Ahc reg path: %ws", a1 + 128);
      Registry = AhcCacheReadRegistry(a1);
      if ( Registry < 0 )
      {
        AslLogCallPrintf(1, "AhcInitialize", 132, "Failed to initialize cache [%x]", Registry);
        v4 = AhcCacheClear(*(_QWORD *)(a1 + 24), 0);
        v2 = v4;
        if ( v4 < 0 )
        {
          v5 = "Failed to clear cache apphelp data [%x]";
          v6 = 141;
          goto LABEL_9;
        }
        *(_OWORD *)(a1 + 40) = 0;
        *(_OWORD *)(a1 + 56) = 0;
        *(_OWORD *)(a1 + 72) = 0;
        *(_DWORD *)(a1 + 88) = 0;
        *(_DWORD *)(a1 + 40) = 52;
      }
      v8 = AhcCdbCreate(a1);
      v2 = v8;
      if ( v8 < 0 )
      {
        AslLogCallPrintf(1, "AhcInitialize", 160, "Failed to create cdb object [%x]", v8);
        *(_DWORD *)(a1 + 92) = 0;
        goto LABEL_27;
      }
      *(_DWORD *)(a1 + 92) = 1;
      AhcCdbReadRegistry(a1, v9);
      v4 = AhcSdbQueryCreate(a1 + 104);
      v2 = v4;
      if ( v4 >= 0 )
      {
        v4 = CitmInitialize(a1);
        v2 = v4;
        if ( v4 >= 0 )
        {
          *(_DWORD *)(a1 + 96) = 1;
          return 0;
        }
        v5 = "Failed to initialize citm [%x]";
        v6 = 237;
      }
      else
      {
        v5 = "Failed to create SdbQuery object [%x]";
        v6 = 227;
      }
    }
    else
    {
      v5 = "RtlStringCchCopyW failed [%x]";
      v6 = 118;
    }
  }
  else
  {
    v5 = "Failed to create cache object [%x]";
    v6 = 92;
  }
LABEL_9:
  LODWORD(v15) = v4;
  AslLogCallPrintf(1, "AhcInitialize", v6, v5, v15);
LABEL_27:
  v12 = *(_QWORD *)(a1 + 24);
  if ( v12 )
  {
    AhcCacheDelete(v12);
    *(_QWORD *)(a1 + 24) = 0;
  }
  v13 = *(_QWORD *)(a1 + 32);
  if ( v13 )
  {
    AhcCdbDelete(v13);
    *(_QWORD *)(a1 + 32) = 0;
  }
  if ( *(_QWORD *)(a1 + 104) )
  {
    AhcSdbQueryDelete();
    *(_QWORD *)(a1 + 104) = 0;
  }
  CitmShutdown(a1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002a3dc  push    rbx
0x14002a3de  push    rbp
0x14002a3df  push    rsi
0x14002a3e0  push    rdi
0x14002a3e1  push    r14
0x14002a3e3  sub     rsp, 40h
0x14002a3e7  cmp     dword ptr [rcx+2C0h], 0
0x14002a3ee  mov     rbx, rcx
0x14002a3f1  jnz     short loc_14002A401
0x14002a3f3  lea     rax, AhcLogVPrintf
0x14002a3fa  mov     cs:g_AslLogPfnVPrintf, rax
0x14002a401  mov     r8d, 47h ; 'G'
0x14002a407  lea     rbp, aAhcinitialize; "AhcInitialize"
0x14002a40e  lea     r9, aEnter; "Enter."
0x14002a415  mov     rdx, rbp
0x14002a418  lea     ecx, [r8-44h]
0x14002a41c  call    AslLogCallPrintf
0x14002a421  lea     rcx, [rbx+10h]
0x14002a425  call    AhcLockCreate
0x14002a42a  mov     edi, eax
0x14002a42c  test    eax, eax
0x14002a42e  js      loc_14002A636
0x14002a434  cmp     qword ptr [rbx+10h], 0
0x14002a439  jz      loc_14002A636
0x14002a43f  lea     rsi, [rbx+2D0h]
0x14002a446  mov     rcx, rsi
0x14002a449  call    AhcLockCreate
0x14002a44e  mov     edi, eax
0x14002a450  test    eax, eax
0x14002a452  js      loc_14002A627
0x14002a458  cmp     qword ptr [rsi], 0
0x14002a45c  jz      loc_14002A627
0x14002a462  lea     r8, [rbx+48h]
0x14002a466  lea     rcx, [rbx+18h]
0x14002a46a  call    AhcCacheCreate
0x14002a46f  mov     edi, eax
0x14002a471  test    eax, eax
0x14002a473  jns     short loc_14002A498
0x14002a475  lea     r9, aFailedToCreate_7; "Failed to create cache object [%x]"
0x14002a47c  mov     r8d, 5Ch ; '\'
0x14002a482  mov     ecx, 1
0x14002a487  mov     rdx, rbp
0x14002a48a  mov     dword ptr [rsp+68h+var_48], eax
0x14002a48e  call    AslLogCallPrintf
0x14002a493  jmp     loc_14002A656
0x14002a498  xorps   xmm0, xmm0
0x14002a49b  lea     rsi, [rbx+80h]
0x14002a4a2  movups  xmmword ptr [rbx+28h], xmm0
0x14002a4a6  xor     eax, eax
0x14002a4a8  xor     r9d, r9d
0x14002a4ab  movups  xmmword ptr [rbx+38h], xmm0
0x14002a4af  mov     [rsp+68h+var_38], rax
0x14002a4b4  lea     r8, aRegistryMachin_6; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14002a4bb  movups  xmmword ptr [rbx+48h], xmm0
0x14002a4bf  mov     [rbx+58h], eax
0x14002a4c2  lea     rcx, SourceString; "AppCompatCache"
0x14002a4c9  mov     [rsp+68h+var_40], 208h
0x14002a4d1  xor     edx, edx
0x14002a4d3  mov     dword ptr [rbx+28h], 34h ; '4'
0x14002a4da  mov     [rsp+68h+var_48], rsi
0x14002a4df  call    cs:__imp_RtlGetPersistedStateLocation
0x14002a4e6  nop     dword ptr [rax+rax+00h]
0x14002a4eb  test    eax, eax
0x14002a4ed  jns     short loc_14002A51B
0x14002a4ef  lea     r8, aRegistryMachin_6; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x14002a4f6  mov     edx, 104h; cchDest
0x14002a4fb  mov     rcx, rsi; pszDest
0x14002a4fe  call    RtlStringCchCopyW
0x14002a503  mov     edi, eax
0x14002a505  test    eax, eax
0x14002a507  jns     short loc_14002A51B
0x14002a509  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14002a510  mov     r8d, 76h ; 'v'
0x14002a516  jmp     loc_14002A482
0x14002a51b  mov     r8d, 7Bh ; '{'
0x14002a521  mov     [rsp+68h+var_48], rsi
0x14002a526  lea     r9, aAhcRegPathWs; "Ahc reg path: %ws"
0x14002a52d  mov     rdx, rbp
0x14002a530  lea     ecx, [r8-78h]
0x14002a534  call    AslLogCallPrintf
0x14002a539  mov     rcx, rbx
0x14002a53c  call    AhcCacheReadRegistry
0x14002a541  mov     esi, 1
0x14002a546  test    eax, eax
0x14002a548  jns     short loc_14002A5A5
0x14002a54a  lea     r9, aFailedToInitia_9; "Failed to initialize cache [%x]"
0x14002a551  mov     dword ptr [rsp+68h+var_48], eax
0x14002a555  mov     r8d, 84h
0x14002a55b  mov     rdx, rbp
0x14002a55e  mov     ecx, esi
0x14002a560  call    AslLogCallPrintf
0x14002a565  mov     rcx, [rbx+18h]
0x14002a569  xor     edx, edx
0x14002a56b  call    AhcCacheClear
0x14002a570  mov     edi, eax
0x14002a572  test    eax, eax
0x14002a574  jns     short loc_14002A58A
0x14002a576  lea     r9, aFailedToClearC_1; "Failed to clear cache apphelp data [%x]"
0x14002a57d  mov     r8d, 8Dh
0x14002a583  mov     ecx, esi
0x14002a585  jmp     loc_14002A487
0x14002a58a  xorps   xmm0, xmm0
0x14002a58d  xor     eax, eax
0x14002a58f  movups  xmmword ptr [rbx+28h], xmm0
0x14002a593  movups  xmmword ptr [rbx+38h], xmm0
0x14002a597  movups  xmmword ptr [rbx+48h], xmm0
0x14002a59b  mov     [rbx+58h], eax
0x14002a59e  mov     dword ptr [rbx+28h], 34h ; '4'
0x14002a5a5  mov     rcx, rbx
0x14002a5a8  call    AhcCdbCreate
0x14002a5ad  mov     edi, eax
0x14002a5af  test    eax, eax
0x14002a5b1  jns     short loc_14002A5D7
0x14002a5b3  lea     r9, aFailedToCreate_0; "Failed to create cdb object [%x]"
0x14002a5ba  mov     dword ptr [rsp+68h+var_48], eax
0x14002a5be  mov     r8d, 0A0h
0x14002a5c4  mov     rdx, rbp
0x14002a5c7  mov     ecx, esi
0x14002a5c9  call    AslLogCallPrintf
0x14002a5ce  mov     dword ptr [rbx+5Ch], 0
0x14002a5d5  jmp     short loc_14002A656
0x14002a5d7  mov     rcx, rbx
0x14002a5da  mov     [rbx+5Ch], esi
0x14002a5dd  call    AhcCdbReadRegistry
0x14002a5e2  lea     rcx, [rbx+68h]
0x14002a5e6  call    AhcSdbQueryCreate
0x14002a5eb  mov     edi, eax
0x14002a5ed  test    eax, eax
0x14002a5ef  jns     short loc_14002A600
0x14002a5f1  lea     r9, aFailedToCreate_1; "Failed to create SdbQuery object [%x]"
0x14002a5f8  mov     r8d, 0E3h
0x14002a5fe  jmp     short loc_14002A583
0x14002a600  mov     rcx, rbx
0x14002a603  call    CitmInitialize
0x14002a608  mov     edi, eax
0x14002a60a  test    eax, eax
0x14002a60c  jns     short loc_14002A620
0x14002a60e  lea     r9, aFailedToInitia_7; "Failed to initialize citm [%x]"
0x14002a615  mov     r8d, 0EDh
0x14002a61b  jmp     loc_14002A583
0x14002a620  mov     [rbx+60h], esi
0x14002a623  xor     edi, edi
0x14002a625  jmp     short loc_14002A6A0
0x14002a627  mov     r8d, 51h ; 'Q'
0x14002a62d  lea     r9, aFailedToInitia_5; "Failed to initialize shared sdb handle "...
0x14002a634  jmp     short loc_14002A643
0x14002a636  mov     r8d, 4Bh ; 'K'
0x14002a63c  lea     r9, aFailedToInitia_10; "Failed to initialize quirks table lock"
0x14002a643  mov     esi, 1
0x14002a648  mov     rdx, rbp
0x14002a64b  mov     ecx, esi
0x14002a64d  call    AslLogCallPrintf
0x14002a652  test    edi, edi
0x14002a654  jns     short loc_14002A6A0
0x14002a656  mov     rcx, [rbx+18h]
0x14002a65a  test    rcx, rcx
0x14002a65d  jz      short loc_14002A66C
0x14002a65f  call    AhcCacheDelete
0x14002a664  mov     qword ptr [rbx+18h], 0
0x14002a66c  mov     rcx, [rbx+20h]
0x14002a670  test    rcx, rcx
0x14002a673  jz      short loc_14002A682
0x14002a675  call    AhcCdbDelete
0x14002a67a  mov     qword ptr [rbx+20h], 0
0x14002a682  mov     rcx, [rbx+68h]
0x14002a686  test    rcx, rcx
0x14002a689  jz      short loc_14002A698
0x14002a68b  call    AhcSdbQueryDelete
0x14002a690  mov     qword ptr [rbx+68h], 0
0x14002a698  mov     rcx, rbx
0x14002a69b  call    CitmShutdown
0x14002a6a0  mov     eax, edi
0x14002a6a2  add     rsp, 40h
0x14002a6a6  pop     r14
0x14002a6a8  pop     rdi
0x14002a6a9  pop     rsi
0x14002a6aa  pop     rbp
0x14002a6ab  pop     rbx
0x14002a6ac  retn
```
