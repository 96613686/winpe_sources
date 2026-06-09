# RdVhd::Uvhd::CProfileHelper::DeleteRegistryTree(ushort const *)

- ea: `0x1800561c0`
- end: `0x180056446`
- name: `?DeleteRegistryTree@CProfileHelper@Uvhd@RdVhd@@AEBAJPEBG@Z`
- size: `646`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CProfileHelper *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180056450`

## callees

- `0x1800141e8`
- `0x1800488e4`
- `0x180048ab0`
- `0x180048b28`
- `0x1800561c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056293`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180056293`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180056314`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180056314`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056433`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056393`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180056433`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800563ac`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800563ac`

## string_xrefs

- `0x1800562bf`: `RegOpenKeyEx(%s), reg tree root`
- `0x180056340`: `RegDeleteTree(%s), reg tree root`
- `0x1800563d8`: `RegDeleteKeyW(%s), reg tree root`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CProfileHelper::DeleteRegistryTree(
        RdVhd::Uvhd::CProfileHelper *this,
        const unsigned __int16 *a2)
{
  signed int v3; // ebx
  LSTATUS v4; // eax
  int v5; // r9d
  RdVhd::Uvhd::CUvhdDiskManager *v6; // rcx
  int v7; // edx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        147,
        WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids,
        L"szRegTreeRoot is NULL");
    }
    v3 = -2147024809;
    goto LABEL_43;
  }
  if ( *a2 )
  {
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x1000Bu, &hKey);
    v3 = v4;
    if ( v4 && (v4 & 0xFFFF0000) == 0 )
    {
      if ( v4 > 0 )
        v3 = v4 | 0x80070000;
      v3 = v3 & 0x8000FFFF | 0x50930000;
    }
    _TraceNrmRdvVmEx(L"UVHD", (unsigned int)v3, L"RegOpenKeyEx(%s), reg tree root");
    if ( v3 >= 0 )
    {
      v8 = RegDeleteTreeW(hKey, 0);
      v3 = v8;
      if ( v8 && (v8 & 0xFFFF0000) == 0 )
      {
        if ( v8 > 0 )
          v3 = v8 | 0x80070000;
        v3 = v3 & 0x8000FFFF | 0x50940000;
      }
      _TraceNrmRdvVmEx(L"UVHD", (unsigned int)v3, L"RegDeleteTree(%s), reg tree root");
      if ( v3 >= 0 )
      {
        RegCloseKey(hKey);
        hKey = 0;
        v9 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, a2);
        v3 = v9;
        if ( v9 && (v9 & 0xFFFF0000) == 0 )
        {
          if ( v9 > 0 )
            v3 = v9 | 0x80070000;
          v3 = v3 & 0x8000FFFF | 0x50950000;
        }
        _TraceNrmRdvVmEx(L"UVHD", (unsigned int)v3, L"RegDeleteKeyW(%s), reg tree root");
        if ( v3 >= 0 )
          goto LABEL_43;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_43;
        }
        v7 = 151;
      }
      else
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_43;
        }
        v7 = 150;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_43;
      }
      v7 = 149;
    }
    WPP_SF_Sd(*((_QWORD *)v6 + 2), v7, (unsigned int)WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, v5, v3);
    goto LABEL_43;
  }
  v3 = -2147024809;
  if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return (unsigned int)v3;
  }
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids, 2147942487LL);
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800561c0  mov     [rsp+arg_8], rbx
0x1800561c5  mov     [rsp+hKey], rcx
0x1800561ca  push    rdi
0x1800561cb  sub     rsp, 30h
0x1800561cf  mov     rdi, rdx
0x1800561d2  mov     [rsp+38h+hKey], 0
0x1800561db  test    rdx, rdx
0x1800561de  jnz     short loc_180056225
0x1800561e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800561e7  lea     rax, WPP_GLOBAL_Control
0x1800561ee  cmp     rcx, rax
0x1800561f1  jz      short loc_18005621B
0x1800561f3  test    byte ptr [rcx+1Ch], 4
0x1800561f7  jz      short loc_18005621B
0x1800561f9  cmp     byte ptr [rcx+19h], 2
0x1800561fd  jb      short loc_18005621B
0x1800561ff  mov     rcx, [rcx+10h]
0x180056203  lea     r9, aSzregtreerootI; "szRegTreeRoot is NULL"
0x18005620a  mov     edx, 93h
0x18005620f  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x180056216  call    WPP_SF_S
0x18005621b  mov     ebx, 80070057h
0x180056220  jmp     loc_180056429
0x180056225  xor     eax, eax
0x180056227  cmp     ax, [rdx]
0x18005622a  jnz     short loc_180056279
0x18005622c  mov     ebx, 80070057h
0x180056231  mov     rcx, cs:WPP_GLOBAL_Control
0x180056238  lea     rax, WPP_GLOBAL_Control
0x18005623f  cmp     rcx, rax
0x180056242  jz      loc_180056439
0x180056248  test    byte ptr [rcx+1Ch], 4
0x18005624c  jz      loc_180056439
0x180056252  cmp     byte ptr [rcx+19h], 2
0x180056256  jb      loc_180056439
0x18005625c  mov     rcx, [rcx+10h]
0x180056260  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x180056267  mov     edx, 94h
0x18005626c  mov     r9d, ebx
0x18005626f  call    WPP_SF_d
0x180056274  jmp     loc_180056429
0x180056279  lea     rax, [rsp+38h+hKey]
0x18005627e  mov     r9d, 1000Bh; samDesired
0x180056284  xor     r8d, r8d; ulOptions
0x180056287  mov     [rsp+38h+phkResult], rax; phkResult
0x18005628c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180056293  call    cs:__imp_RegOpenKeyExW
0x180056299  mov     ebx, eax
0x18005629b  test    eax, eax
0x18005629d  jz      short loc_1800562BC
0x18005629f  test    eax, 0FFFF0000h
0x1800562a4  jnz     short loc_1800562BC
0x1800562a6  test    eax, eax
0x1800562a8  jle     short loc_1800562B0
0x1800562aa  or      ebx, 80070000h
0x1800562b0  and     ebx, 0D093FFFFh
0x1800562b6  or      ebx, 50930000h
0x1800562bc  mov     r9, rdi
0x1800562bf  lea     r8, aRegopenkeyexSR; "RegOpenKeyEx(%s), reg tree root"
0x1800562c6  mov     edx, ebx; int
0x1800562c8  lea     rcx, aUvhd; "UVHD"
0x1800562cf  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800562d4  test    ebx, ebx
0x1800562d6  jns     short loc_18005630D
0x1800562d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800562df  lea     rax, WPP_GLOBAL_Control
0x1800562e6  cmp     rcx, rax
0x1800562e9  jz      loc_180056429
0x1800562ef  test    byte ptr [rcx+1Ch], 4
0x1800562f3  jz      loc_180056429
0x1800562f9  cmp     byte ptr [rcx+19h], 2
0x1800562fd  jb      loc_180056429
0x180056303  mov     edx, 95h
0x180056308  jmp     loc_180056415
0x18005630d  mov     rcx, [rsp+38h+hKey]; hKey
0x180056312  xor     edx, edx; lpSubKey
0x180056314  call    cs:__imp_RegDeleteTreeW
0x18005631a  mov     ebx, eax
0x18005631c  test    eax, eax
0x18005631e  jz      short loc_18005633D
0x180056320  test    eax, 0FFFF0000h
0x180056325  jnz     short loc_18005633D
0x180056327  test    eax, eax
0x180056329  jle     short loc_180056331
0x18005632b  or      ebx, 80070000h
0x180056331  and     ebx, 0D094FFFFh
0x180056337  or      ebx, 50940000h
0x18005633d  mov     r9, rdi
0x180056340  lea     r8, aRegdeletetreeS; "RegDeleteTree(%s), reg tree root"
0x180056347  mov     edx, ebx; int
0x180056349  lea     rcx, aUvhd; "UVHD"
0x180056350  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x180056355  test    ebx, ebx
0x180056357  jns     short loc_18005638E
0x180056359  mov     rcx, cs:WPP_GLOBAL_Control
0x180056360  lea     rax, WPP_GLOBAL_Control
0x180056367  cmp     rcx, rax
0x18005636a  jz      loc_180056429
0x180056370  test    byte ptr [rcx+1Ch], 4
0x180056374  jz      loc_180056429
0x18005637a  cmp     byte ptr [rcx+19h], 2
0x18005637e  jb      loc_180056429
0x180056384  mov     edx, 96h
0x180056389  jmp     loc_180056415
0x18005638e  mov     rcx, [rsp+38h+hKey]; hKey
0x180056393  call    cs:__imp_RegCloseKey
0x180056399  mov     rdx, rdi; lpSubKey
0x18005639c  mov     [rsp+38h+hKey], 0
0x1800563a5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800563ac  call    cs:__imp_RegDeleteKeyW
0x1800563b2  mov     ebx, eax
0x1800563b4  test    eax, eax
0x1800563b6  jz      short loc_1800563D5
0x1800563b8  test    eax, 0FFFF0000h
0x1800563bd  jnz     short loc_1800563D5
0x1800563bf  test    eax, eax
0x1800563c1  jle     short loc_1800563C9
0x1800563c3  or      ebx, 80070000h
0x1800563c9  and     ebx, 0D095FFFFh
0x1800563cf  or      ebx, 50950000h
0x1800563d5  mov     r9, rdi
0x1800563d8  lea     r8, aRegdeletekeywS; "RegDeleteKeyW(%s), reg tree root"
0x1800563df  mov     edx, ebx; int
0x1800563e1  lea     rcx, aUvhd; "UVHD"
0x1800563e8  call    ?_TraceNrmRdvVmEx@@YAXPEBGJ0ZZ; _TraceNrmRdvVmEx(ushort const *,long,ushort const *,...)
0x1800563ed  test    ebx, ebx
0x1800563ef  jns     short loc_180056429
0x1800563f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800563f8  lea     rax, WPP_GLOBAL_Control
0x1800563ff  cmp     rcx, rax
0x180056402  jz      short loc_180056429
0x180056404  test    byte ptr [rcx+1Ch], 4
0x180056408  jz      short loc_180056429
0x18005640a  cmp     byte ptr [rcx+19h], 2
0x18005640e  jb      short loc_180056429
0x180056410  mov     edx, 97h
0x180056415  mov     rcx, [rcx+10h]
0x180056419  lea     r8, WPP_8bdd996048cc3a3a6adb915db88b6959_Traceguids
0x180056420  mov     dword ptr [rsp+38h+phkResult], ebx
0x180056424  call    WPP_SF_Sd
0x180056429  mov     rcx, [rsp+38h+hKey]; hKey
0x18005642e  test    rcx, rcx
0x180056431  jz      short loc_180056439
0x180056433  call    cs:__imp_RegCloseKey
0x180056439  mov     eax, ebx
0x18005643b  mov     rbx, [rsp+38h+arg_8]
0x180056440  add     rsp, 30h
0x180056444  pop     rdi
0x180056445  retn
```
