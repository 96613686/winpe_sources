# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x40b08b`
- end: `0x40b15e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CGJPBG_NPA_KPA_N@Z`
- size: `211`
- prototype: `int __userpurge@<eax>(size_t@<ecx>, const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x40c3ba`

## callees

- `0x402625`
- `0x402dc4`
- `0x40adfa`
- `0x40ae18`
- `0x40ae71`
- `0x40af70`
- `0x40b08b`
- `0x40cb60`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x40b0e0`
- `KERNEL32!OpenSemaphoreW` at `0x40b0e0`
- `KERNEL32!GetLastError` at `0x40b0ec`
- `KERNEL32!GetLastError` at `0x40b0ec`

## pseudocode

```c
int __userpurge wil::details_abi::SemaphoreValue::TryGetValueInternal@<eax>(
        size_t a1@<ecx>,
        const unsigned __int16 *a2,
        bool a3,
        unsigned __int64 *a4,
        bool *a5)
{
  int LastError; // edi
  HANDLE v6; // esi
  wil::details::in1diag3 *v7; // ecx
  void *ValueFromSemaphore; // eax
  wil::details::in1diag3 *v9; // ecx
  unsigned int v11; // [esp+0h] [ebp-220h]
  unsigned int v12; // [esp+0h] [ebp-220h]
  void *v13; // [esp+0h] [ebp-220h]
  const unsigned __int16 *v14; // [esp+4h] [ebp-21Ch]
  const unsigned __int16 *v15; // [esp+4h] [ebp-21Ch]
  int *v16; // [esp+4h] [ebp-21Ch]
  const char *v17; // [esp+4h] [ebp-21Ch]
  const char *v18; // [esp+8h] [ebp-218h]
  WCHAR Name[262]; // [esp+10h] [ebp-210h] BYREF
  int retaddr; // [esp+224h] [ebp+4h]

  LastError = 0;
  *(_DWORD *)a2 = 0;
  *((_DWORD *)a2 + 1) = 0;
  StringCchCopyW(a1, v11, v14);
  StringCchCatW(260, Name, L"_p0", v12, v15);
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  if ( v6 )
  {
    ValueFromSemaphore = (void *)wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, v16);
    LastError = (int)ValueFromSemaphore;
    if ( (int)ValueFromSemaphore >= 0 )
    {
      LastError = 0;
      *(_QWORD *)a2 = 0;
LABEL_9:
      wil::details::CloseHandle(v6, v13);
      return LastError;
    }
    wil::details::in1diag3::Return_Hr(retaddr, v9, ValueFromSemaphore, (unsigned int)v13, v17, (int)v18);
  }
  else if ( GetLastError() != 2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(v7, v13, (unsigned int)v16, v18);
  }
  if ( v6 )
    goto LABEL_9;
  return LastError;
}

```

## disassembly

```asm
0x40b08b  mov     edi, edi
0x40b08d  push    ebp
0x40b08e  mov     ebp, esp
0x40b090  and     esp, 0FFFFFFF8h
0x40b093  sub     esp, 214h
0x40b099  mov     eax, ___security_cookie
0x40b09e  xor     eax, esp
0x40b0a0  mov     [esp+214h+var_4], eax
0x40b0a7  push    ebx; int
0x40b0a8  mov     ebx, [ebp+arg_0]
0x40b0ab  push    esi; char *
0x40b0ac  push    edi; void *
0x40b0ad  xor     edi, edi
0x40b0af  mov     esi, 104h
0x40b0b4  push    ecx; cchDest
0x40b0b5  mov     edx, esi
0x40b0b7  mov     [ebx], edi
0x40b0b9  lea     ecx, [esp+224h+Name]
0x40b0bd  mov     [ebx+4], edi
0x40b0c0  call    ?StringCchCopyW@@YGJPAGIPBG@Z; StringCchCopyW(ushort *,uint,ushort const *)
0x40b0c5  push    offset aP0; "_p0"
0x40b0ca  mov     edx, esi
0x40b0cc  lea     ecx, [esp+224h+Name]
0x40b0d0  call    ?StringCchCatW@@YGJPAGIPBG@Z; StringCchCatW(ushort *,uint,ushort const *)
0x40b0d5  lea     eax, [esp+220h+Name]
0x40b0d9  push    eax; lpName
0x40b0da  push    edi; bInheritHandle
0x40b0db  push    1F0003h; dwDesiredAccess
0x40b0e0  call    ds:__imp__OpenSemaphoreW@12; OpenSemaphoreW(x,x,x)
0x40b0e6  mov     esi, eax
0x40b0e8  test    esi, esi
0x40b0ea  jnz     short loc_40B109
0x40b0ec  call    ds:__imp__GetLastError@0; GetLastError()
0x40b0f2  cmp     eax, 2
0x40b0f5  jz      short loc_40B12D
0x40b0f7  push    ecx; this
0x40b0f8  mov     ecx, [ebp+4]
0x40b0fb  mov     edx, 0D0h
0x40b100  call    ?Return_GetLastError@in1diag3@details@wil@@YGJPAXIPBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x40b105  mov     edi, eax
0x40b107  jmp     short loc_40B12D
0x40b109  lea     edx, [esp+220h+var_214]
0x40b10d  mov     [esp+220h+var_214], edi
0x40b111  mov     ecx, esi
0x40b113  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CGJPAXPAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x40b118  mov     edi, eax
0x40b11a  test    edi, edi
0x40b11c  jns     short loc_40B133
0x40b11e  push    edi; void *
0x40b11f  push    ecx; this
0x40b120  mov     ecx, [ebp+4]
0x40b123  mov     edx, 0D6h
0x40b128  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x40b12d  test    esi, esi
0x40b12f  jz      short loc_40B145
0x40b131  jmp     short loc_40B13F
0x40b133  mov     eax, [esp+220h+var_214]
0x40b137  xor     edi, edi
0x40b139  cdq
0x40b13a  mov     [ebx], eax
0x40b13c  mov     [ebx+4], edx
0x40b13f  push    esi; hObject
0x40b140  call    ?CloseHandle@details@wil@@YGXPAX@Z; wil::details::CloseHandle(void *)
0x40b145  mov     ecx, [esp+220h+var_4]
0x40b14c  mov     eax, edi
0x40b14e  pop     edi
0x40b14f  pop     esi
0x40b150  pop     ebx
0x40b151  xor     ecx, esp; StackCookie
0x40b153  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40b158  mov     esp, ebp
0x40b15a  pop     ebp
0x40b15b  retn    8
```
