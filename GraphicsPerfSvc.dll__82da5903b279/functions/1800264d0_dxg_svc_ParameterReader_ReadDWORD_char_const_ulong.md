# dxg::svc::ParameterReader::ReadDWORD(char const *,ulong)

- ea: `0x1800264d0`
- end: `0x18002655d`
- name: `?ReadDWORD@ParameterReader@svc@dxg@@QEBAKPEBDK@Z`
- size: `141`
- prototype: `unsigned int(dxg::svc::ParameterReader *__hidden this, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011630`

## callees

- `0x18001bfb0`
- `0x1800264d0`
- `0x180026564`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18002651d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18002651d`

## string_xrefs

- `0x18002652c`: `onecoreuap\windows\directx\dxg\common\servicehelpers\parameters.cpp`

## pseudocode

```c
__int64 __fastcall dxg::svc::ParameterReader::ReadDWORD(HKEY *this, CHAR *a2, unsigned int a3)
{
  HKEY v3; // rcx
  unsigned int v4; // ebx
  unsigned int ValueA; // eax
  unsigned int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v10; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+60h] [rbp+18h] BYREF

  v3 = *this;
  v4 = a3;
  if ( v3 )
  {
    v11 = 0;
    v10 = 4;
    ValueA = RegGetValueA(v3, 0, a2, 0x18u, 0, &v11, &v10);
    if ( ValueA )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\parameters.cpp",
        (const char *)ValueA,
        v8);
    else
      v4 = v11;
  }
  dxg::svc::LogParameterRead((dxg::svc *)a2, (const char *)v4, a3);
  return v4;
}

```

## disassembly

```asm
0x1800264d0  mov     r11, rsp
0x1800264d3  mov     [r11+10h], rbx
0x1800264d7  push    rdi
0x1800264d8  sub     rsp, 40h
0x1800264dc  mov     rcx, [rcx]; hkey
0x1800264df  mov     ebx, r8d
0x1800264e2  mov     rdi, rdx
0x1800264e5  test    rcx, rcx
0x1800264e8  jz      short loc_180026546
0x1800264ea  lea     rax, [r11+8]
0x1800264ee  mov     [rsp+48h+arg_10], 0
0x1800264f6  mov     [r11-18h], rax
0x1800264fa  mov     r8, rdx; lpValue
0x1800264fd  lea     rax, [r11+18h]
0x180026501  mov     [rsp+48h+arg_0], 4
0x180026509  mov     [r11-20h], rax
0x18002650d  mov     r9d, 18h; dwFlags
0x180026513  xor     edx, edx; lpSubKey
0x180026515  mov     qword ptr [r11-28h], 0
0x18002651d  call    cs:__imp_RegGetValueA
0x180026523  test    eax, eax
0x180026525  jz      short loc_180026542
0x180026527  mov     rcx, [rsp+48h]; this
0x18002652c  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180026533  mov     r9d, eax; char *
0x180026536  mov     edx, 3Ah ; ':'; void *
0x18002653b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180026540  jmp     short loc_180026546
0x180026542  mov     ebx, [rsp+48h+arg_10]
0x180026546  mov     edx, ebx; char *
0x180026548  mov     rcx, rdi; this
0x18002654b  call    ?LogParameterRead@svc@dxg@@YAXPEBDK@Z; dxg::svc::LogParameterRead(char const *,ulong)
0x180026550  mov     eax, ebx
0x180026552  mov     rbx, [rsp+48h+arg_8]
0x180026557  add     rsp, 40h
0x18002655b  pop     rdi
0x18002655c  retn
```
