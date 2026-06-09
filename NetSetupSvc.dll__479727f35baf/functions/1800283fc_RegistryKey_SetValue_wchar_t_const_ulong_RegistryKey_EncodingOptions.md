# RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)

- ea: `0x1800283fc`
- end: `0x1800284f7`
- name: `?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z`
- size: `251`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009cfc`
- `0x18000c5e0`
- `0x18001ea44`
- `0x18001f984`
- `0x180021650`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008c78`
- `0x1800268d4`
- `0x180028284`
- `0x1800283fc`
- `0x180028804`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028494`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028494`

## pseudocode

```c
void __fastcall RegistryKey::SetValue(HKEY *a1, const wchar_t *a2, int a3, int a4)
{
  LSTATUS v6; // ebx
  int v7; // r8d
  BYTE pExceptionObject[208]; // [rsp+30h] [rbp-128h] BYREF
  BYTE Data[8]; // [rsp+100h] [rbp-58h] BYREF
  BYTE v10[64]; // [rsp+108h] [rbp-50h] BYREF

  *(_DWORD *)Data = a3;
  if ( a4 )
  {
    if ( a4 == 1 )
    {
      swprintf_s<30>(v10, L"%u");
      RegistryKey::SetValue(a1, a2, v10);
    }
  }
  else
  {
    v6 = RegSetValueExW(*a1, a2, 0, 4u, Data, 4u);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_SDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v7, (_DWORD)a2, Data[0], v6);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v6);
      throw (Win32Exception *)pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x1800283fc  mov     r11, rsp
0x1800283ff  mov     [r11+20h], rbx
0x180028403  push    rdi
0x180028404  sub     rsp, 150h
0x18002840b  mov     rax, cs:__security_cookie
0x180028412  xor     rax, rsp
0x180028415  mov     [rsp+158h+var_10], rax
0x18002841d  mov     [r11-58h], r8d
0x180028421  mov     rdi, rdx
0x180028424  mov     rbx, rcx
0x180028427  test    r9d, r9d
0x18002842a  jz      short loc_180028476
0x18002842c  cmp     r9d, 1
0x180028430  jnz     short loc_180028455
0x180028432  lea     rdx, aU; "%u"
0x180028439  lea     rcx, [r11-50h]
0x18002843d  call    ??$swprintf_s@$0BO@@@YAHAEAY0BO@_WPEB_WZZ; swprintf_s<30>(wchar_t (&)[30],wchar_t const *,...)
0x180028442  lea     r8, [rsp+158h+var_50]; wchar_t *
0x18002844a  mov     rdx, rdi; wchar_t *
0x18002844d  mov     rcx, rbx; this
0x180028450  call    ?SetValue@RegistryKey@@QEBAXPEB_W0@Z; RegistryKey::SetValue(wchar_t const *,wchar_t const *)
0x180028455  mov     rcx, [rsp+158h+var_10]
0x18002845d  xor     rcx, rsp; StackCookie
0x180028460  call    __security_check_cookie
0x180028465  mov     rbx, [rsp+158h+arg_18]
0x18002846d  add     rsp, 150h
0x180028474  pop     rdi
0x180028475  retn
0x180028476  mov     rcx, [rcx]; hKey
0x180028479  lea     rax, [rsp+158h+Data]
0x180028481  mov     r9d, 4; dwType
0x180028487  xor     r8d, r8d; Reserved
0x18002848a  mov     [rsp+158h+cbData], r9d; cbData
0x18002848f  mov     [rsp+158h+lpData], rax; lpData
0x180028494  call    cs:__imp_RegSetValueExW
0x18002849a  mov     ebx, eax
0x18002849c  test    eax, eax
0x18002849e  jz      short loc_180028455
0x1800284a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284a7  lea     rax, WPP_GLOBAL_Control
0x1800284ae  cmp     rcx, rax
0x1800284b1  jz      short loc_1800284D9
0x1800284b3  cmp     byte ptr [rcx+19h], 2
0x1800284b7  jb      short loc_1800284D9
0x1800284b9  mov     eax, dword ptr [rsp+158h+Data]
0x1800284c0  mov     edx, 27h ; '''
0x1800284c5  mov     rcx, [rcx+10h]
0x1800284c9  mov     r9, rdi
0x1800284cc  mov     [rsp+158h+cbData], ebx
0x1800284d0  mov     dword ptr [rsp+158h+lpData], eax
0x1800284d4  call    WPP_SF_SDD
0x1800284d9  mov     edx, ebx; int
0x1800284db  lea     rcx, [rsp+158h+pExceptionObject]; this
0x1800284e0  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800284e5  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800284ec  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x1800284f1  call    _CxxThrowException_0
```
