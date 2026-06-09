# AddMethodKey(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180028c8c`
- end: `0x180028ee6`
- name: `?AddMethodKey@@YAHPEAUHKEY__@@PEBG111K@Z`
- size: `602`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180028ef0`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180021530`
- `0x180028c8c`
- `0x18002d4cc`
- `0x18002d854`
- `0x18002d934`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180028d29`
- `KERNEL32!GetLastError` at `0x180028e1a`
- `KERNEL32!GetLastError` at `0x180028d29`
- `KERNEL32!GetLastError` at `0x180028e1a`
- `ADVAPI32!RegDeleteKeyW` at `0x180028e8e`
- `ADVAPI32!RegDeleteKeyW` at `0x180028e8e`
- `ADVAPI32!RegCloseKey` at `0x180028dba`
- `ADVAPI32!RegCloseKey` at `0x180028e48`
- `ADVAPI32!RegCloseKey` at `0x180028dba`
- `ADVAPI32!RegCloseKey` at `0x180028e48`

## pseudocode

```c
__int64 __fastcall AddMethodKey(
        HKEY hKey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  HKEY v10; // rax
  HKEY v11; // rbx
  LSTATUS v12; // eax
  _QWORD *v13; // rcx
  int v14; // edx
  unsigned int v15; // eax
  DWORD LastError; // eax
  unsigned int v18; // eax
  int v19; // [rsp+20h] [rbp-58h]
  int v20; // [rsp+20h] [rbp-58h]
  int v21; // [rsp+20h] [rbp-58h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids);
  }
  v10 = (HKEY)OpenRegistryKey(hKey, lpSubKey, 1, 131359);
  v11 = v10;
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    LOBYTE(v12) = GetLastError();
    v13 = WPP_GLOBAL_Control;
    v14 = 40;
LABEL_34:
    WPP_SF_Sd(v13[2], v14, (unsigned int)&WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, (_DWORD)lpSubKey, v12);
    return 0;
  }
  if ( !SetRegistryStringValue(v10, 1u, L"FriendlyName", a3, v19)
    || !SetRegistryStringValue(v11, 1u, L"Function Name", a4, v20)
    || !SetRegistryStringValue(v11, 1u, L"Guid", a5, v21)
    || !(unsigned int)SetRegistryDword(v11, L"Priority", a6) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, LastError);
    }
    v18 = RegCloseKey(v11);
    if ( v18
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, v18);
    }
    v12 = RegDeleteKeyW(hKey, lpSubKey);
    if ( !v12 )
      return 0;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v14 = 44;
    goto LABEL_34;
  }
  v15 = RegCloseKey(v11);
  if ( v15
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_6048c066639239f9f9d6b48872920a8c_Traceguids, v15);
  }
  return 1;
}

```

## disassembly

```asm
0x180028c8c  push    rbx
0x180028c8e  push    rbp
0x180028c8f  push    rsi
0x180028c90  push    rdi
0x180028c91  push    r12
0x180028c93  push    r13
0x180028c95  push    r14
0x180028c97  push    r15
0x180028c99  sub     rsp, 38h
0x180028c9d  mov     rbp, r9
0x180028ca0  mov     rsi, r8
0x180028ca3  mov     rdi, rdx
0x180028ca6  mov     r14, rcx
0x180028ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180028cb0  lea     r12, WPP_GLOBAL_Control
0x180028cb7  mov     r15d, 1000h
0x180028cbd  cmp     rcx, r12
0x180028cc0  jz      short loc_180028CE3
0x180028cc2  test    [rcx+1Ch], r15d
0x180028cc6  jz      short loc_180028CE3
0x180028cc8  cmp     byte ptr [rcx+19h], 5
0x180028ccc  jb      short loc_180028CE3
0x180028cce  mov     rcx, [rcx+10h]
0x180028cd2  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180028cd9  mov     edx, 27h ; '''
0x180028cde  call    WPP_SF_
0x180028ce3  mov     r13d, 1
0x180028ce9  mov     r9d, 2011Fh
0x180028cef  mov     r8d, r13d
0x180028cf2  mov     rdx, rdi
0x180028cf5  mov     rcx, r14
0x180028cf8  call    OpenRegistryKey
0x180028cfd  mov     rbx, rax
0x180028d00  test    rax, rax
0x180028d03  jnz     short loc_180028D44
0x180028d05  mov     rax, cs:WPP_GLOBAL_Control
0x180028d0c  cmp     rax, r12
0x180028d0f  jz      loc_180028ED2
0x180028d15  test    [rax+1Ch], r15d
0x180028d19  jz      loc_180028ED2
0x180028d1f  cmp     byte ptr [rax+19h], 2
0x180028d23  jb      loc_180028ED2
0x180028d29  call    cs:__imp_GetLastError
0x180028d30  nop     dword ptr [rax+rax+00h]
0x180028d35  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d3c  lea     edx, [rbx+28h]
0x180028d3f  jmp     loc_180028EBB
0x180028d44  mov     r9, rsi; unsigned __int16 *
0x180028d47  lea     r8, aFriendlyname; "FriendlyName"
0x180028d4e  mov     edx, r13d; unsigned int
0x180028d51  mov     rcx, rbx; HKEY
0x180028d54  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x180028d59  test    eax, eax
0x180028d5b  jz      loc_180028E02
0x180028d61  mov     r9, rbp; unsigned __int16 *
0x180028d64  lea     r8, aFunctionName; "Function Name"
0x180028d6b  mov     edx, r13d; unsigned int
0x180028d6e  mov     rcx, rbx; HKEY
0x180028d71  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x180028d76  test    eax, eax
0x180028d78  jz      loc_180028E02
0x180028d7e  mov     r9, [rsp+78h+arg_20]; unsigned __int16 *
0x180028d86  lea     r8, aGuid; "Guid"
0x180028d8d  mov     edx, r13d; unsigned int
0x180028d90  mov     rcx, rbx; HKEY
0x180028d93  call    ?SetRegistryStringValue@@YAHPEAUHKEY__@@KPEBG1J@Z; SetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,long)
0x180028d98  test    eax, eax
0x180028d9a  jz      short loc_180028E02
0x180028d9c  mov     r8d, [rsp+78h+arg_28]
0x180028da4  lea     rdx, aPriority; "Priority"
0x180028dab  mov     rcx, rbx
0x180028dae  call    SetRegistryDword
0x180028db3  test    eax, eax
0x180028db5  jz      short loc_180028E02
0x180028db7  mov     rcx, rbx; hKey
0x180028dba  call    cs:__imp_RegCloseKey
0x180028dc1  nop     dword ptr [rax+rax+00h]
0x180028dc6  test    eax, eax
0x180028dc8  jz      short loc_180028DFA
0x180028dca  mov     rcx, cs:WPP_GLOBAL_Control
0x180028dd1  cmp     rcx, r12
0x180028dd4  jz      short loc_180028DFA
0x180028dd6  test    [rcx+1Ch], r15d
0x180028dda  jz      short loc_180028DFA
0x180028ddc  cmp     byte ptr [rcx+19h], 2
0x180028de0  jb      short loc_180028DFA
0x180028de2  mov     rcx, [rcx+10h]
0x180028de6  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180028ded  mov     edx, 2Ah ; '*'
0x180028df2  mov     r9d, eax
0x180028df5  call    WPP_SF_d
0x180028dfa  mov     eax, r13d
0x180028dfd  jmp     loc_180028ED4
0x180028e02  mov     rax, cs:WPP_GLOBAL_Control
0x180028e09  cmp     rax, r12
0x180028e0c  jz      short loc_180028E45
0x180028e0e  test    [rax+1Ch], r15d
0x180028e12  jz      short loc_180028E45
0x180028e14  cmp     byte ptr [rax+19h], 2
0x180028e18  jb      short loc_180028E45
0x180028e1a  call    cs:__imp_GetLastError
0x180028e21  nop     dword ptr [rax+rax+00h]
0x180028e26  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e2d  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180028e34  mov     edx, 29h ; ')'
0x180028e39  mov     r9d, eax
0x180028e3c  mov     rcx, [rcx+10h]
0x180028e40  call    WPP_SF_d
0x180028e45  mov     rcx, rbx; hKey
0x180028e48  call    cs:__imp_RegCloseKey
0x180028e4f  nop     dword ptr [rax+rax+00h]
0x180028e54  test    eax, eax
0x180028e56  jz      short loc_180028E88
0x180028e58  mov     rcx, cs:WPP_GLOBAL_Control
0x180028e5f  cmp     rcx, r12
0x180028e62  jz      short loc_180028E88
0x180028e64  test    [rcx+1Ch], r15d
0x180028e68  jz      short loc_180028E88
0x180028e6a  cmp     byte ptr [rcx+19h], 2
0x180028e6e  jb      short loc_180028E88
0x180028e70  mov     rcx, [rcx+10h]
0x180028e74  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180028e7b  mov     edx, 2Bh ; '+'
0x180028e80  mov     r9d, eax
0x180028e83  call    WPP_SF_d
0x180028e88  mov     rdx, rdi; lpSubKey
0x180028e8b  mov     rcx, r14; hKey
0x180028e8e  call    cs:__imp_RegDeleteKeyW
0x180028e95  nop     dword ptr [rax+rax+00h]
0x180028e9a  test    eax, eax
0x180028e9c  jz      short loc_180028ED2
0x180028e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ea5  cmp     rcx, r12
0x180028ea8  jz      short loc_180028ED2
0x180028eaa  test    [rcx+1Ch], r15d
0x180028eae  jz      short loc_180028ED2
0x180028eb0  cmp     byte ptr [rcx+19h], 2
0x180028eb4  jb      short loc_180028ED2
0x180028eb6  mov     edx, 2Ch ; ','
0x180028ebb  mov     rcx, [rcx+10h]
0x180028ebf  lea     r8, WPP_6048c066639239f9f9d6b48872920a8c_Traceguids
0x180028ec6  mov     r9, rdi
0x180028ec9  mov     [rsp+78h+var_58], eax
0x180028ecd  call    WPP_SF_Sd
0x180028ed2  xor     eax, eax
0x180028ed4  add     rsp, 38h
0x180028ed8  pop     r15
0x180028eda  pop     r14
0x180028edc  pop     r13
0x180028ede  pop     r12
0x180028ee0  pop     rdi
0x180028ee1  pop     rsi
0x180028ee2  pop     rbp
0x180028ee3  pop     rbx
0x180028ee4  retn
```
