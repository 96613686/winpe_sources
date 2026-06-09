# VBAddIn::AddInSetRegValue(char *)

- ea: `0x1800a667c`
- end: `0x1800a6831`
- name: `?AddInSetRegValue@VBAddIn@@AEAAJPEAD@Z`
- size: `437`
- prototype: `__int64 __fastcall(VBAddIn *__hidden this, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800a456c`

## callees

- `0x18001606c`
- `0x1800a667c`
- `0x1800a7178`
- `0x180379380`

## import_xrefs

- `MSVCR100!free` at `0x1800a6808`
- `MSVCR100!free` at `0x1800a6816`
- `MSVCR100!free` at `0x1800a6808`
- `MSVCR100!free` at `0x1800a6816`
- `MSVCR100!malloc` at `0x1800a66eb`
- `MSVCR100!malloc` at `0x1800a66eb`
- `KERNEL32!lstrlenA` at `0x1800a66d2`
- `KERNEL32!lstrlenA` at `0x1800a66dd`
- `KERNEL32!lstrlenA` at `0x1800a66d2`
- `KERNEL32!lstrlenA` at `0x1800a66dd`
- `KERNEL32!RaiseException` at `0x1800a679e`
- `KERNEL32!RaiseException` at `0x1800a679e`
- `USER32!wsprintfA` at `0x1800a670e`
- `USER32!wsprintfA` at `0x1800a670e`
- `ADVAPI32!RegSetValueExA` at `0x1800a67c6`
- `ADVAPI32!RegSetValueExA` at `0x1800a67c6`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a6731`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a6765`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a6731`
- `ADVAPI32!RegOpenKeyExA` at `0x1800a6765`
- `ADVAPI32!RegCloseKey` at `0x1800a67ea`
- `ADVAPI32!RegCloseKey` at `0x1800a67fa`
- `ADVAPI32!RegCloseKey` at `0x1800a67ea`
- `ADVAPI32!RegCloseKey` at `0x1800a67fa`

## pseudocode

```c
__int64 __fastcall VBAddIn::AddInSetRegValue(VBAddIn *this, const BYTE *a2)
{
  int v2; // edi
  VBAddInManager *v4; // rcx
  const BYTE *v5; // r14
  CHAR *v6; // rbx
  CHAR *AddinRegLocation; // rsi
  int v8; // ebx
  int v9; // eax
  CHAR *v10; // rax
  LSTATUS v11; // eax
  __int64 v12; // rcx
  LSTATUS v13; // eax
  int v14; // eax
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v4 = (VBAddInManager *)*((_QWORD *)this + 18);
  hKey = 0;
  phkResult = 0;
  v5 = (const BYTE *)&Class;
  v6 = 0;
  if ( a2 )
    v5 = a2;
  AddinRegLocation = VBAddInManager::GetAddinRegLocation(v4);
  if ( AddinRegLocation )
  {
    v8 = lstrlenA(*((LPCSTR *)this + 9));
    v9 = lstrlenA(AddinRegLocation);
    v10 = (CHAR *)malloc(v9 + v8 + 2);
    v6 = v10;
    if ( v10 )
    {
      wsprintfA(v10, "%s\\%s", AddinRegLocation, *((const char **)this + 9));
      v11 = RegOpenKeyExA(*((HKEY *)this + 19), v6, 0, 0x20019u, &phkResult);
      v2 = HrFromRegError(v11);
      if ( v2 >= 0 )
      {
        if ( RegOpenKeyExA(*((HKEY *)this + 19), v6, 0, 0xF003Fu, &hKey) == 70 )
        {
          v2 = -2146768216;
        }
        else
        {
          v12 = -1;
          do
            ++v12;
          while ( v5[v12] );
          if ( (unsigned int)v12 != v12 )
          {
            RaiseException(0xC0000095, 1u, 1u, (const ULONG_PTR *)v12);
            LODWORD(v12) = (_DWORD)hKey;
          }
          v13 = RegSetValueExA(hKey, aDescription_1, 0, 1u, v5, v12 + 1);
          v14 = HrFromRegError(v13);
          if ( v14 == 70 )
            v14 = -2146768216;
          v2 = v14;
        }
      }
    }
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( AddinRegLocation )
    free(AddinRegLocation);
  if ( v6 )
    free(v6);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800a667c  mov     [rsp+arg_10], rbx
0x1800a6681  mov     [rsp+arg_18], rbp
0x1800a6686  push    rsi
0x1800a6687  push    rdi
0x1800a6688  push    r14
0x1800a668a  mov     eax, 30h
0x1800a668f  call    _alloca_probe
0x1800a6694  sub     rsp, rax
0x1800a6697  xor     edi, edi
0x1800a6699  mov     rbp, rcx
0x1800a669c  mov     rcx, [rcx+90h]; this
0x1800a66a3  and     [rsp+48h+hKey], rdi
0x1800a66a8  and     [rsp+48h+arg_8], rdi
0x1800a66ad  lea     r14, Class
0x1800a66b4  xor     ebx, ebx
0x1800a66b6  test    rdx, rdx
0x1800a66b9  cmovnz  r14, rdx
0x1800a66bd  call    ?GetAddinRegLocation@VBAddInManager@@QEAAPEADXZ; VBAddInManager::GetAddinRegLocation(void)
0x1800a66c2  mov     rsi, rax
0x1800a66c5  test    rax, rax
0x1800a66c8  jz      loc_1800A67E0
0x1800a66ce  mov     rcx, [rbp+48h]; lpString
0x1800a66d2  call    cs:__imp_lstrlenA
0x1800a66d8  mov     rcx, rsi; lpString
0x1800a66db  mov     ebx, eax
0x1800a66dd  call    cs:__imp_lstrlenA
0x1800a66e3  lea     ecx, [rbx+2]
0x1800a66e6  add     ecx, eax
0x1800a66e8  movsxd  rcx, ecx; Size
0x1800a66eb  call    cs:__imp_malloc
0x1800a66f1  mov     rbx, rax
0x1800a66f4  test    rax, rax
0x1800a66f7  jz      loc_1800A67E0
0x1800a66fd  mov     r9, [rbp+48h]
0x1800a6701  lea     rdx, aSS_1; "%s\\%s"
0x1800a6708  mov     r8, rsi
0x1800a670b  mov     rcx, rax; LPSTR
0x1800a670e  call    cs:__imp_wsprintfA
0x1800a6714  mov     rcx, [rbp+98h]; hKey
0x1800a671b  lea     rax, [rsp+48h+arg_8]
0x1800a6720  mov     r9d, 20019h; samDesired
0x1800a6726  xor     r8d, r8d; ulOptions
0x1800a6729  mov     rdx, rbx; lpSubKey
0x1800a672c  mov     [rsp+48h+phkResult], rax; phkResult
0x1800a6731  call    cs:__imp_RegOpenKeyExA
0x1800a6737  mov     ecx, eax; int
0x1800a6739  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a673e  mov     edi, eax
0x1800a6740  test    eax, eax
0x1800a6742  js      loc_1800A67E0
0x1800a6748  mov     rcx, [rbp+98h]; hKey
0x1800a674f  lea     rax, [rsp+48h+hKey]
0x1800a6754  mov     r9d, 0F003Fh; samDesired
0x1800a675a  xor     r8d, r8d; ulOptions
0x1800a675d  mov     rdx, rbx; lpSubKey
0x1800a6760  mov     [rsp+48h+phkResult], rax; phkResult
0x1800a6765  call    cs:__imp_RegOpenKeyExA
0x1800a676b  cmp     eax, 46h ; 'F'
0x1800a676e  jnz     short loc_1800A6777
0x1800a6770  mov     edi, 800AEAA8h
0x1800a6775  jmp     short loc_1800A67E0
0x1800a6777  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800a677b  inc     rcx
0x1800a677e  cmp     byte ptr [r14+rcx], 0
0x1800a6783  jnz     short loc_1800A677B
0x1800a6785  mov     eax, ecx
0x1800a6787  mov     edi, 1
0x1800a678c  cmp     rax, rcx
0x1800a678f  jz      short loc_1800A67A8
0x1800a6791  mov     r9, rcx; lpArguments
0x1800a6794  mov     r8d, edi; nNumberOfArguments
0x1800a6797  mov     edx, edi; dwExceptionFlags
0x1800a6799  mov     ecx, 0C0000095h; dwExceptionCode
0x1800a679e  call    cs:__imp_RaiseException
0x1800a67a4  mov     ecx, dword ptr [rsp+48h+hKey]
0x1800a67a8  lea     eax, [rcx+1]
0x1800a67ab  mov     rcx, [rsp+48h+hKey]; hKey
0x1800a67b0  lea     rdx, aDescription_1; "Description"
0x1800a67b7  mov     [rsp+48h+cbData], eax; cbData
0x1800a67bb  mov     r9d, edi; dwType
0x1800a67be  xor     r8d, r8d; Reserved
0x1800a67c1  mov     [rsp+48h+phkResult], r14; lpData
0x1800a67c6  call    cs:__imp_RegSetValueExA
0x1800a67cc  mov     ecx, eax; int
0x1800a67ce  call    ?HrFromRegError@@YAJJ@Z; HrFromRegError(long)
0x1800a67d3  mov     edi, 800AEAA8h
0x1800a67d8  cmp     eax, 46h ; 'F'
0x1800a67db  cmovz   eax, edi
0x1800a67de  mov     edi, eax
0x1800a67e0  mov     rcx, [rsp+48h+arg_8]; hKey
0x1800a67e5  test    rcx, rcx
0x1800a67e8  jz      short loc_1800A67F0
0x1800a67ea  call    cs:__imp_RegCloseKey
0x1800a67f0  mov     rcx, [rsp+48h+hKey]; hKey
0x1800a67f5  test    rcx, rcx
0x1800a67f8  jz      short loc_1800A6800
0x1800a67fa  call    cs:__imp_RegCloseKey
0x1800a6800  test    rsi, rsi
0x1800a6803  jz      short loc_1800A680E
0x1800a6805  mov     rcx, rsi; Block
0x1800a6808  call    cs:__imp_free
0x1800a680e  test    rbx, rbx
0x1800a6811  jz      short loc_1800A681C
0x1800a6813  mov     rcx, rbx; Block
0x1800a6816  call    cs:__imp_free
0x1800a681c  mov     rbx, [rsp+48h+arg_10]
0x1800a6821  mov     rbp, [rsp+48h+arg_18]
0x1800a6826  mov     eax, edi
0x1800a6828  add     rsp, 30h
0x1800a682c  pop     r14
0x1800a682e  pop     rdi
0x1800a682f  pop     rsi
0x1800a6830  retn
```
