# DeleteSubkeys(ushort const *,ushort const *,ushort const *)

- ea: `0x18000e494`
- end: `0x18000e5ba`
- name: `?DeleteSubkeys@@YAJPEBG00@Z`
- size: `294`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fba0`

## callees

- `0x18000a644`
- `0x18000e40c`
- `0x18000e494`
- `0x18000fc50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e511`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e559`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e59d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e559`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e59d`

## pseudocode

```c
__int64 __fastcall DeleteSubkeys(LPCWSTR lpSubKey, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HKEY v6; // rdi
  int v7; // ebx
  HKEY v8; // rdx
  unsigned __int16 *v9; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-58h]
  unsigned int v12; // [rsp+28h] [rbp-50h]
  struct _SECURITY_ATTRIBUTES *v13; // [rsp+30h] [rbp-48h]
  unsigned int *v14; // [rsp+38h] [rbp-40h]
  HKEY hKey[4]; // [rsp+40h] [rbp-38h] BYREF
  HKEY v16; // [rsp+98h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  v6 = 0;
  hKey[1] = 0;
  hKey[2] = 0;
  v16 = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &v16);
  if ( !v7 )
  {
    hKey[0] = v16;
    v7 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, a2);
    if ( !v7 )
      v7 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, v8, a3, v9, phkResult, v12, v13, v14);
    v6 = hKey[0];
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      v6 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  if ( v6 )
    RegCloseKey(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e494  mov     [rsp+arg_0], rbx
0x18000e499  mov     [rsp+arg_8], rbp
0x18000e49e  push    rsi
0x18000e49f  push    rdi
0x18000e4a0  push    r15
0x18000e4a2  sub     rsp, 60h
0x18000e4a6  mov     rsi, r8
0x18000e4a9  mov     rbp, rdx
0x18000e4ac  mov     rbx, rcx
0x18000e4af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e4b6  lea     r15, WPP_GLOBAL_Control
0x18000e4bd  cmp     rcx, r15
0x18000e4c0  jz      short loc_18000E4DD
0x18000e4c2  test    byte ptr [rcx+1Ch], 20h
0x18000e4c6  jz      short loc_18000E4DD
0x18000e4c8  mov     rcx, [rcx+10h]
0x18000e4cc  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000e4d3  mov     edx, 61h ; 'a'
0x18000e4d8  call    WPP_SF_
0x18000e4dd  xor     edi, edi
0x18000e4df  lea     rax, [rsp+78h+arg_18]
0x18000e4e7  mov     r9d, 2001Fh; samDesired
0x18000e4ed  mov     [rsp+78h+var_30], rdi
0x18000e4f2  xor     r8d, r8d; ulOptions
0x18000e4f5  mov     [rsp+78h+var_28], rdi
0x18000e4fa  mov     rdx, rbx; lpSubKey
0x18000e4fd  mov     [rsp+78h+arg_18], rdi
0x18000e505  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e50c  mov     [rsp+78h+phkResult], rax; unsigned int
0x18000e511  call    cs:__imp_RegOpenKeyExW
0x18000e517  mov     ebx, eax
0x18000e519  test    eax, eax
0x18000e51b  jnz     short loc_18000E561
0x18000e51d  mov     rax, [rsp+78h+arg_18]
0x18000e525  lea     rcx, [rsp+78h+hKey]; this
0x18000e52a  mov     rdx, rbp; unsigned __int16 *
0x18000e52d  mov     [rsp+78h+hKey], rax
0x18000e532  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000e537  mov     ebx, eax
0x18000e539  test    eax, eax
0x18000e53b  jnz     short loc_18000E54C
0x18000e53d  mov     r8, rsi; unsigned __int16 *
0x18000e540  lea     rcx, [rsp+78h+hKey]; this
0x18000e545  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000e54a  mov     ebx, eax
0x18000e54c  mov     rdi, [rsp+78h+hKey]
0x18000e551  test    rdi, rdi
0x18000e554  jz      short loc_18000E561
0x18000e556  mov     rcx, rdi; hKey
0x18000e559  call    cs:__imp_RegCloseKey
0x18000e55f  xor     edi, edi
0x18000e561  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e568  cmp     rcx, r15
0x18000e56b  jz      short loc_18000E588
0x18000e56d  test    byte ptr [rcx+1Ch], 20h
0x18000e571  jz      short loc_18000E588
0x18000e573  mov     rcx, [rcx+10h]
0x18000e577  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000e57e  mov     edx, 62h ; 'b'
0x18000e583  call    WPP_SF_
0x18000e588  test    ebx, ebx
0x18000e58a  jle     short loc_18000E595
0x18000e58c  movzx   ebx, bx
0x18000e58f  or      ebx, 80070000h
0x18000e595  test    rdi, rdi
0x18000e598  jz      short loc_18000E5A3
0x18000e59a  mov     rcx, rdi; hKey
0x18000e59d  call    cs:__imp_RegCloseKey
0x18000e5a3  lea     r11, [rsp+78h+var_18]
0x18000e5a8  mov     eax, ebx
0x18000e5aa  mov     rbx, [r11+20h]
0x18000e5ae  mov     rbp, [r11+28h]
0x18000e5b2  mov     rsp, r11
0x18000e5b5  pop     r15
0x18000e5b7  pop     rdi
0x18000e5b8  pop     rsi
0x18000e5b9  retn
```
