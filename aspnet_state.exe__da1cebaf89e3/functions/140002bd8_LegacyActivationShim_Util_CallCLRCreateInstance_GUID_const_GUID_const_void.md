# LegacyActivationShim::Util::CallCLRCreateInstance(_GUID const &,_GUID const &,void * *)

- ea: `0x140002bd8`
- end: `0x140002c50`
- name: `?CallCLRCreateInstance@Util@LegacyActivationShim@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `120`
- prototype: `__int64 __fastcall(LegacyActivationShim::Util *this, HINSTANCE *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140002dfc`
- `0x140002e88`

## callees

- `0x140002bd8`
- `0x1400031e0`
- `0x140006590`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140002c0f`
- `KERNEL32!GetProcAddress` at `0x140002c0f`
- `KERNEL32!GetLastError` at `0x140002c1a`
- `KERNEL32!GetLastError` at `0x140002c1a`

## string_xrefs

- `0x140002c08`: `CLRCreateInstance`

## pseudocode

```c
__int64 __fastcall LegacyActivationShim::Util::CallCLRCreateInstance(
        LegacyActivationShim::Util *this,
        HINSTANCE *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  FARPROC ProcAddress; // rax
  signed int LastError; // ecx
  HMODULE hModule; // [rsp+48h] [rbp+20h] BYREF

  hModule = 0;
  result = LegacyActivationShim::Util::GetMSCOREE((LegacyActivationShim::Util *)&hModule, a2);
  if ( (int)result >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, "CLRCreateInstance");
    if ( ProcAddress )
    {
      return ((__int64 (__fastcall *)(LegacyActivationShim::Util *, HINSTANCE *, const struct _GUID *))ProcAddress)(
               this,
               a2,
               a3);
    }
    else
    {
      LastError = GetLastError();
      result = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        return (unsigned int)LastError;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002bd8  mov     rax, rsp
0x140002bdb  mov     [rax+8], rbx
0x140002bdf  mov     [rax+10h], rsi
0x140002be3  push    rdi
0x140002be4  sub     rsp, 20h
0x140002be8  and     qword ptr [rax+20h], 0
0x140002bed  mov     rsi, rcx
0x140002bf0  lea     rcx, [rax+20h]; this
0x140002bf4  mov     rbx, r8
0x140002bf7  mov     rdi, rdx
0x140002bfa  call    ?GetMSCOREE@Util@LegacyActivationShim@@YAJPEAPEAUHINSTANCE__@@@Z; LegacyActivationShim::Util::GetMSCOREE(HINSTANCE__ * *)
0x140002bff  test    eax, eax
0x140002c01  js      short loc_140002C40
0x140002c03  mov     rcx, [rsp+28h+hModule]; hModule
0x140002c08  lea     rdx, aClrcreateinsta; "CLRCreateInstance"
0x140002c0f  call    cs:__imp_GetProcAddress
0x140002c15  test    rax, rax
0x140002c18  jnz     short loc_140002C31
0x140002c1a  call    cs:__imp_GetLastError
0x140002c20  mov     ecx, eax
0x140002c22  movzx   eax, ax
0x140002c25  or      eax, 80070000h
0x140002c2a  test    ecx, ecx
0x140002c2c  cmovle  eax, ecx
0x140002c2f  jmp     short loc_140002C40
0x140002c31  mov     r8, rbx
0x140002c34  mov     rdx, rdi
0x140002c37  mov     rcx, rsi
0x140002c3a  call    cs:__guard_dispatch_icall_fptr
0x140002c40  mov     rbx, [rsp+28h+arg_0]
0x140002c45  mov     rsi, [rsp+28h+arg_8]
0x140002c4a  add     rsp, 20h
0x140002c4e  pop     rdi
0x140002c4f  retn
```
