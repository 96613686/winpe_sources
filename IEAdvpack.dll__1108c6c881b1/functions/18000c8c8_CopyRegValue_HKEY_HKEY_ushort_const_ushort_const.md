# CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)

- ea: `0x18000c8c8`
- end: `0x18000c993`
- name: `?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z`
- size: `203`
- prototype: `__int64 __fastcall(HKEY, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010d50`
- `0x1800115b0`
- `0x180011940`

## callees

- `0x18000c8c8`
- `0x18001b980`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000c926`
- `ADVAPI32!RegQueryValueExW` at `0x18000c926`
- `ADVAPI32!RegSetValueExW` at `0x18000c965`
- `ADVAPI32!RegSetValueExW` at `0x18000c965`

## pseudocode

```c
__int64 __fastcall CopyRegValue(HKEY a1, HKEY a2, const unsigned __int16 *a3, const unsigned __int16 *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  DWORD Type; // [rsp+30h] [rbp-858h] BYREF
  DWORD cbData[3]; // [rsp+34h] [rbp-854h] BYREF
  _WORD Data[1032]; // [rsp+40h] [rbp-848h] BYREF

  cbData[0] = 2048;
  Type = 0;
  Data[1024] = 0;
  v6 = 0;
  if ( !RegQueryValueExW(a1, a3, 0, &Type, (LPBYTE)Data, cbData) )
  {
    v7 = -1;
    do
      ++v7;
    while ( Data[v7] );
    if ( !RegSetValueExW(a2, a4, 0, Type, (const BYTE *)Data, 2 * v7 + 2) )
      return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x18000c8c8  push    rbx
0x18000c8ca  push    rbp
0x18000c8cb  push    rsi
0x18000c8cc  push    rdi
0x18000c8cd  sub     rsp, 868h
0x18000c8d4  mov     rax, cs:__security_cookie
0x18000c8db  xor     rax, rsp
0x18000c8de  mov     [rsp+888h+var_38], rax
0x18000c8e6  mov     r10, r8
0x18000c8e9  mov     [rsp+888h+cbData], 800h
0x18000c8f1  xor     ebp, ebp
0x18000c8f3  lea     rax, [rsp+888h+cbData]
0x18000c8f8  mov     [rsp+888h+lpcbData], rax; lpcbData
0x18000c8fd  mov     rsi, r9
0x18000c900  lea     rax, [rsp+888h+Data]
0x18000c905  mov     [rsp+888h+Type], ebp
0x18000c909  mov     rdi, rdx
0x18000c90c  mov     [rsp+888h+lpData], rax; lpData
0x18000c911  lea     r9, [rsp+888h+Type]; lpType
0x18000c916  mov     [rsp+888h+var_48], bp
0x18000c91e  xor     r8d, r8d; lpReserved
0x18000c921  mov     rdx, r10; lpValueName
0x18000c924  mov     ebx, ebp
0x18000c926  call    cs:__imp_RegQueryValueExW
0x18000c92c  test    eax, eax
0x18000c92e  jnz     short loc_18000C975
0x18000c930  lea     rcx, [rsp+888h+Data]
0x18000c935  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c939  inc     rax
0x18000c93c  cmp     [rcx+rax*2], bp
0x18000c940  jnz     short loc_18000C939
0x18000c942  mov     r9d, [rsp+888h+Type]; dwType
0x18000c947  lea     eax, ds:2[rax*2]
0x18000c94e  mov     dword ptr [rsp+888h+lpcbData], eax; cbData
0x18000c952  xor     r8d, r8d; Reserved
0x18000c955  lea     rax, [rsp+888h+Data]
0x18000c95a  mov     rdx, rsi; lpValueName
0x18000c95d  mov     rcx, rdi; hKey
0x18000c960  mov     [rsp+888h+lpData], rax; lpData
0x18000c965  call    cs:__imp_RegSetValueExW
0x18000c96b  test    eax, eax
0x18000c96d  mov     ecx, 1
0x18000c972  cmovz   ebx, ecx
0x18000c975  mov     eax, ebx
0x18000c977  mov     rcx, [rsp+888h+var_38]
0x18000c97f  xor     rcx, rsp; StackCookie
0x18000c982  call    __security_check_cookie
0x18000c987  add     rsp, 868h
0x18000c98e  pop     rdi
0x18000c98f  pop     rsi
0x18000c990  pop     rbp
0x18000c991  pop     rbx
0x18000c992  retn
```
