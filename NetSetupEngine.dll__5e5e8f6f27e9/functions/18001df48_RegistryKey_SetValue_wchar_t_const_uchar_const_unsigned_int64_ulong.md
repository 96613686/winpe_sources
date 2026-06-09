# RegistryKey::SetValue(wchar_t const *,uchar const *,unsigned __int64,ulong)

- ea: `0x18001df48`
- end: `0x18001dfe0`
- name: `?SetValue@RegistryKey@@QEBAXPEB_WPEBE_KK@Z`
- size: `152`
- prototype: `void(RegistryKey *__hidden this, const wchar_t *, const unsigned __int8 *, unsigned __int64, unsigned int)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001c010`
- `0x18001ef74`
- `0x18003fc90`
- `0x18004ca1c`
- `0x1800644a0`
- `0x18006a7d8`
- `0x18006e9f4`
- `0x180079e9c`
- `0x18007bd74`

## callees

- `0x18001df48`
- `0x180052620`
- `0x180052698`
- `0x180065035`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001df70`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001df70`

## pseudocode

```c
void __fastcall RegistryKey::SetValue(
        HKEY *this,
        const wchar_t *a2,
        const unsigned __int8 *lpData,
        DWORD cbData,
        DWORD dwType)
{
  int v5; // edi
  LSTATUS v6; // ebx
  _BYTE pExceptionObject[216]; // [rsp+30h] [rbp-D8h] BYREF

  v5 = (int)a2;
  v6 = RegSetValueExW(*this, a2, 0, dwType, lpData, cbData);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids,
        v5,
        v6);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v6);
    throw (Win32Exception *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18001df48  mov     [rsp+arg_0], rbx
0x18001df4d  push    rdi
0x18001df4e  sub     rsp, 100h
0x18001df55  mov     rcx, [rcx]; hKey
0x18001df58  mov     rdi, rdx
0x18001df5b  mov     [rsp+108h+cbData], r9d; cbData
0x18001df60  mov     r9d, [rsp+108h+dwType]; dwType
0x18001df68  mov     [rsp+108h+lpData], r8; lpData
0x18001df6d  xor     r8d, r8d; Reserved
0x18001df70  call    cs:__imp_RegSetValueExW
0x18001df76  mov     ebx, eax
0x18001df78  test    eax, eax
0x18001df7a  jz      short loc_18001DFCF
0x18001df7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df83  lea     rax, WPP_GLOBAL_Control
0x18001df8a  cmp     rcx, rax
0x18001df8d  jz      short loc_18001DFB1
0x18001df8f  cmp     byte ptr [rcx+19h], 2
0x18001df93  jb      short loc_18001DFB1
0x18001df95  mov     rcx, [rcx+10h]
0x18001df99  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x18001dfa0  mov     edx, 2Dh ; '-'
0x18001dfa5  mov     dword ptr [rsp+108h+lpData], ebx
0x18001dfa9  mov     r9, rdi
0x18001dfac  call    WPP_SF_Sd
0x18001dfb1  mov     edx, ebx; int
0x18001dfb3  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18001dfb8  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18001dfbd  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18001dfc4  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18001dfc9  call    _CxxThrowException_0
0x18001dfcf  mov     rbx, [rsp+108h+arg_0]
0x18001dfd7  add     rsp, 100h
0x18001dfde  pop     rdi
0x18001dfdf  retn
```
