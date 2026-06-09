# CInputDllRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x180033180`
- end: `0x1800332c2`
- name: `?Create@CInputDllRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `322`
- prototype: `__int64 __fastcall(CInputDllRegKey *this, HKEY hKey, LPCWSTR lpSubKey, unsigned __int16 *, DWORD dwDisposition)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005500`
- `0x180032ae4`
- `0x180032c44`

## callees

- `0x180007fc0`
- `0x180033180`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003320c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003322a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003320c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003322a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800331f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800332a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800331f4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800332a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180033252`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180033252`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInputDllRegKey::Create(
        CInputDllRegKey *this,
        HKEY hKey,
        LPCWSTR lpSubKey,
        unsigned __int16 *a4,
        DWORD dwDisposition)
{
  HKEY v6; // rsi
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  HKEY v10; // rcx
  LSTATUS v11; // eax
  HKEY hKeya; // [rsp+78h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+20h] BYREF

  dwDisposition = 0;
  v6 = hKey;
  phkResult = 0;
  hKeya = 0;
  if ( hKey == HKEY_CURRENT_USER && !RegOpenCurrentUser(0x2001Fu, &hKeya) )
    v6 = hKeya;
  v8 = RegCreateKeyExW(v6, lpSubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
  v9 = v8;
  if ( !v8 )
  {
    v10 = (HKEY)*((_QWORD *)this + 1);
    v9 = 0;
    if ( !v10 )
    {
LABEL_6:
      *((_QWORD *)this + 1) = phkResult;
      goto LABEL_7;
    }
    v11 = RegCloseKey(v10);
LABEL_5:
    v9 = v11;
    goto LABEL_6;
  }
  if ( v8 == 5 )
  {
    v9 = RegCreateKeyExW(v6, lpSubKey, 0, 0, 4u, 0x2001Fu, 0, &phkResult, &dwDisposition);
    if ( !v9 )
    {
      v11 = CInputDllRegKey::Close(this);
      goto LABEL_5;
    }
  }
LABEL_7:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v9;
}

```

## disassembly

```asm
0x180033180  mov     rax, rsp
0x180033183  mov     [rax+8], rbx
0x180033187  mov     [rax+18h], rbp
0x18003318b  mov     [rax+20h], r9
0x18003318f  push    rsi
0x180033190  push    rdi
0x180033191  push    r14
0x180033193  sub     rsp, 50h
0x180033197  xor     r14d, r14d
0x18003319a  mov     rbp, r8
0x18003319d  mov     [rax+28h], r14d
0x1800331a1  mov     rsi, rdx
0x1800331a4  mov     [rax+20h], r14
0x1800331a8  mov     rdi, rcx
0x1800331ab  mov     [rax+10h], r14
0x1800331af  cmp     rdx, 0FFFFFFFF80000001h
0x1800331b6  jz      loc_180033248
0x1800331bc  lea     rax, [rsp+68h+dwDisposition]
0x1800331c4  xor     r9d, r9d; lpClass
0x1800331c7  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x1800331cc  xor     r8d, r8d; Reserved
0x1800331cf  lea     rax, [rsp+68h+arg_18]
0x1800331d7  mov     rdx, rbp; lpSubKey
0x1800331da  mov     [rsp+68h+phkResult], rax; phkResult
0x1800331df  mov     rcx, rsi; hKey
0x1800331e2  mov     [rsp+68h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800331e7  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x1800331ef  mov     [rsp+68h+dwOptions], r14d; dwOptions
0x1800331f4  call    cs:__imp_RegCreateKeyExW
0x1800331fa  mov     ebx, eax
0x1800331fc  test    eax, eax
0x1800331fe  jnz     short loc_180033265
0x180033200  mov     rcx, [rdi+8]; hKey
0x180033204  mov     ebx, r14d
0x180033207  test    rcx, rcx
0x18003320a  jz      short loc_180033214
0x18003320c  call    cs:__imp_RegCloseKey
0x180033212  mov     ebx, eax
0x180033214  mov     rax, [rsp+68h+arg_18]
0x18003321c  mov     [rdi+8], rax
0x180033220  mov     rcx, [rsp+68h+hKey]; hKey
0x180033225  test    rcx, rcx
0x180033228  jz      short loc_180033230
0x18003322a  call    cs:__imp_RegCloseKey
0x180033230  mov     rbp, [rsp+68h+arg_10]
0x180033238  mov     eax, ebx
0x18003323a  mov     rbx, [rsp+68h+arg_0]
0x18003323f  add     rsp, 50h
0x180033243  pop     r14
0x180033245  pop     rdi
0x180033246  pop     rsi
0x180033247  retn
0x180033248  lea     rdx, [rsp+68h+hKey]; phkResult
0x18003324d  mov     ecx, 2001Fh; samDesired
0x180033252  call    cs:__imp_RegOpenCurrentUser
0x180033258  test    eax, eax
0x18003325a  cmovz   rsi, [rsp+68h+hKey]
0x180033260  jmp     loc_1800331BC
0x180033265  cmp     eax, 5
0x180033268  jnz     short loc_180033220
0x18003326a  lea     rax, [rsp+68h+dwDisposition]
0x180033272  xor     r9d, r9d; lpClass
0x180033275  mov     [rsp+68h+lpdwDisposition], rax; lpdwDisposition
0x18003327a  xor     r8d, r8d; Reserved
0x18003327d  lea     rax, [rsp+68h+arg_18]
0x180033285  mov     rdx, rbp; lpSubKey
0x180033288  mov     [rsp+68h+phkResult], rax; phkResult
0x18003328d  mov     rcx, rsi; hKey
0x180033290  mov     [rsp+68h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180033295  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x18003329d  mov     [rsp+68h+dwOptions], 4; dwOptions
0x1800332a5  call    cs:__imp_RegCreateKeyExW
0x1800332ab  mov     ebx, eax
0x1800332ad  test    eax, eax
0x1800332af  jnz     loc_180033220
0x1800332b5  mov     rcx, rdi; this
0x1800332b8  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800332bd  jmp     loc_180033212
```
