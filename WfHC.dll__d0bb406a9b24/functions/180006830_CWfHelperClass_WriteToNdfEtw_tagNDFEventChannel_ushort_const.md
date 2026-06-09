# CWfHelperClass::WriteToNdfEtw(tagNDFEventChannel,ushort const *,...)

- ea: `0x180006830`
- end: `0x1800068ec`
- name: `?WriteToNdfEtw@CWfHelperClass@@AEAAXW4tagNDFEventChannel@@PEBGZZ`
- size: `188`
- prototype: `int(__int64, unsigned int, const wchar_t *, ...)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180004500`
- `0x1800049d0`
- `0x180005990`
- `0x180005a50`

## callees

- `0x180006830`
- `0x18000c5b0`
- `0x18000e010`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000688f`
- `msvcrt!_vsnwprintf` at `0x18000688f`

## pseudocode

```c
int CWfHelperClass::WriteToNdfEtw(__int64 a1, unsigned int a2, const wchar_t *a3, ...)
{
  const wchar_t *v3; // rax
  const wchar_t *v6; // r8
  wchar_t Buffer[264]; // [rsp+40h] [rbp-238h] BYREF
  va_list Args; // [rsp+298h] [rbp+20h] BYREF

  va_start(Args, a3);
  v3 = a3;
  if ( *(_QWORD *)(a1 + 120) && a3 )
  {
    v6 = (const wchar_t *)&qword_1800117E0;
    if ( v3 )
      v6 = v3;
    LODWORD(v3) = _vsnwprintf(Buffer, 0x103u, v6, Args);
    if ( (unsigned int)v3 < 0x104 )
    {
      if ( (_DWORD)v3 == 259 )
        Buffer[259] = 0;
      LODWORD(v3) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, const wchar_t *, wchar_t *))(**(_QWORD **)(a1 + 120)
                                                                                                  + 24LL))(
                      *(_QWORD *)(a1 + 120),
                      a2,
                      0,
                      L"WindowsFirewallHelperClass",
                      Buffer);
    }
  }
  return (int)v3;
}

```

## disassembly

```asm
0x180006830  mov     [rsp+arg_10], r8
0x180006835  mov     qword ptr [rsp+Args], r9
0x18000683a  push    rbx
0x18000683b  push    rdi
0x18000683c  sub     rsp, 268h
0x180006843  mov     rax, cs:__security_cookie
0x18000684a  xor     rax, rsp
0x18000684d  mov     [rsp+278h+var_28], rax
0x180006855  cmp     qword ptr [rcx+78h], 0
0x18000685a  mov     rax, r8
0x18000685d  mov     edi, edx
0x18000685f  mov     rbx, rcx
0x180006862  jz      short loc_1800068D2
0x180006864  test    rax, rax
0x180006867  jz      short loc_1800068D2
0x180006869  lea     r8, qword_1800117E0
0x180006870  mov     [rsp+278h+var_248], 0
0x180006879  cmovnz  r8, rax; Format
0x18000687d  lea     r9, [rsp+278h+Args]; Args
0x180006885  mov     edx, 103h; BufferCount
0x18000688a  lea     rcx, [rsp+278h+Buffer]; Buffer
0x18000688f  call    cs:__imp__vsnwprintf
0x180006895  test    eax, eax
0x180006897  js      short loc_1800068D2
0x180006899  cmp     eax, 103h
0x18000689e  ja      short loc_1800068D2
0x1800068a0  jnz     short loc_1800068AC
0x1800068a2  xor     eax, eax
0x1800068a4  mov     [rsp+278h+var_32], ax
0x1800068ac  mov     rcx, [rbx+78h]
0x1800068b0  lea     rdx, [rsp+278h+Buffer]
0x1800068b5  mov     [rsp+278h+var_258], rdx
0x1800068ba  lea     r9, aWindowsfirewal; "WindowsFirewallHelperClass"
0x1800068c1  xor     r8d, r8d
0x1800068c4  mov     edx, edi
0x1800068c6  mov     rax, [rcx]
0x1800068c9  mov     rax, [rax+18h]
0x1800068cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068d2  mov     rcx, [rsp+278h+var_28]
0x1800068da  xor     rcx, rsp; StackCookie
0x1800068dd  call    __security_check_cookie
0x1800068e2  add     rsp, 268h
0x1800068e9  pop     rdi
0x1800068ea  pop     rbx
0x1800068eb  retn
```
