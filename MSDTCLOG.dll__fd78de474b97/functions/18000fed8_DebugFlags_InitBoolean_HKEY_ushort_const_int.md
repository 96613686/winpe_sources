# DebugFlags::InitBoolean(HKEY__ *,ushort const *,int *)

- ea: `0x18000fed8`
- end: `0x18000ffb9`
- name: `?InitBoolean@DebugFlags@@CAXPEAUHKEY__@@PEBGPEAH@Z`
- size: `225`
- prototype: `void __fastcall(HKEY hKey, LPCWSTR lpValueName, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010070`

## callees

- `0x18000fed8`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ff98`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ff98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ff20`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ff20`

## pseudocode

```c
void __fastcall DebugFlags::InitBoolean(HKEY hKey, LPCWSTR lpValueName, int *a3)
{
  int v6; // eax
  bool v7; // cf
  DWORD cbData[4]; // [rsp+30h] [rbp-128h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-118h] BYREF

  cbData[0] = 240;
  if ( RegQueryValueExW(hKey, lpValueName, 0, 0, Data, cbData) )
  {
    v7 = *a3 != 0;
    *(_WORD *)&Data[2] = 0;
    *(_WORD *)Data = v7 ? 89 : 78;
    RegSetValueExW(hKey, lpValueName, 0, 1u, Data, 4u);
  }
  else if ( cbData[0] >= 2 )
  {
    v6 = *(_WORD *)Data & 0xFFDF;
    if ( v6 == 78 )
    {
      *a3 = 0;
    }
    else if ( v6 == 89 )
    {
      *a3 = 1;
    }
  }
}

```

## disassembly

```asm
0x18000fed8  push    rbx
0x18000feda  push    rsi
0x18000fedb  push    rdi
0x18000fedc  sub     rsp, 140h
0x18000fee3  mov     rax, cs:__security_cookie
0x18000feea  xor     rax, rsp
0x18000feed  mov     [rsp+158h+var_28], rax
0x18000fef5  lea     rax, [rsp+158h+cbData]
0x18000fefa  mov     [rsp+158h+cbData], 0F0h
0x18000ff02  mov     [rsp+158h+lpcbData], rax; lpcbData
0x18000ff07  mov     rbx, r8
0x18000ff0a  lea     rax, [rsp+158h+Data]
0x18000ff0f  xor     r9d, r9d; lpType
0x18000ff12  xor     r8d, r8d; lpReserved
0x18000ff15  mov     [rsp+158h+lpData], rax; lpData
0x18000ff1a  mov     rsi, rdx
0x18000ff1d  mov     rdi, rcx
0x18000ff20  call    cs:__imp_RegQueryValueExW
0x18000ff26  test    eax, eax
0x18000ff28  jnz     short loc_18000FF58
0x18000ff2a  cmp     [rsp+158h+cbData], 2
0x18000ff2f  jb      short loc_18000FF9E
0x18000ff31  mov     eax, dword ptr [rsp+158h+Data]
0x18000ff35  mov     ecx, 4Eh ; 'N'
0x18000ff3a  and     eax, 0FFDFh
0x18000ff3f  cmp     eax, ecx
0x18000ff41  jz      short loc_18000FF50
0x18000ff43  cmp     eax, 59h ; 'Y'
0x18000ff46  jnz     short loc_18000FF9E
0x18000ff48  mov     dword ptr [rbx], 1
0x18000ff4e  jmp     short loc_18000FF9E
0x18000ff50  mov     dword ptr [rbx], 0
0x18000ff56  jmp     short loc_18000FF9E
0x18000ff58  mov     eax, [rbx]
0x18000ff5a  mov     r9d, 1; dwType
0x18000ff60  neg     eax
0x18000ff62  mov     dword ptr [rsp+158h+lpcbData], 4; cbData
0x18000ff6a  mov     rdx, rsi; lpValueName
0x18000ff6d  mov     rcx, rdi; hKey
0x18000ff70  sbb     r8w, r8w
0x18000ff74  xor     eax, eax
0x18000ff76  and     r8w, 0Bh
0x18000ff7b  mov     word ptr [rsp+158h+Data+2], ax
0x18000ff80  add     r8w, 4Eh ; 'N'
0x18000ff85  lea     rax, [rsp+158h+Data]
0x18000ff8a  mov     word ptr [rsp+158h+Data], r8w
0x18000ff90  xor     r8d, r8d; Reserved
0x18000ff93  mov     [rsp+158h+lpData], rax; lpData
0x18000ff98  call    cs:__imp_RegSetValueExW
0x18000ff9e  mov     rcx, [rsp+158h+var_28]
0x18000ffa6  xor     rcx, rsp; StackCookie
0x18000ffa9  call    __security_check_cookie
0x18000ffae  add     rsp, 140h
0x18000ffb5  pop     rdi
0x18000ffb6  pop     rsi
0x18000ffb7  pop     rbx
0x18000ffb8  retn
```
