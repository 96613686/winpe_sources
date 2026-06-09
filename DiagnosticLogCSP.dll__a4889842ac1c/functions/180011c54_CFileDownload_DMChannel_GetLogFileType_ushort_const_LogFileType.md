# CFileDownload_DMChannel::GetLogFileType(ushort const *,LogFileType &)

- ea: `0x180011c54`
- end: `0x180011cce`
- name: `?GetLogFileType@CFileDownload_DMChannel@@IEAAJPEBGAEAW4LogFileType@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(CFileDownload_DMChannel *this, const unsigned __int16 *, enum LogFileType *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011a8c`
- `0x180011e94`

## callees

- `0x18000de80`
- `0x18000f280`
- `0x180011c54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011cac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011cac`

## string_xrefs

- `0x180011ca5`: `MdmConfiguration`

## pseudocode

```c
__int64 __fastcall CFileDownload_DMChannel::GetLogFileType(
        CFileDownload_DMChannel *this,
        const unsigned __int16 *a2,
        enum LogFileType *a3)
{
  unsigned int v5; // esi

  *(_DWORD *)a3 = 3;
  if ( a2 )
  {
    v5 = 0;
    if ( (int)CEventLogChannel::IsChannelRegistered(a2) < 0 )
    {
      if ( (int)CEtwLogCollector::IsCollectorRegistered(a2) < 0 )
      {
        if ( !(unsigned int)_o__wcsicmp(L"MdmConfiguration", a2) )
          *(_DWORD *)a3 = 2;
      }
      else
      {
        *(_DWORD *)a3 = 0;
      }
    }
    else
    {
      *(_DWORD *)a3 = 1;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x180011c54  mov     [rsp+arg_0], rbx
0x180011c59  mov     [rsp+arg_8], rsi
0x180011c5e  push    rdi
0x180011c5f  sub     rsp, 20h
0x180011c63  mov     dword ptr [r8], 3
0x180011c6a  mov     rbx, r8
0x180011c6d  mov     rdi, rdx
0x180011c70  test    rdx, rdx
0x180011c73  jnz     short loc_180011C7C
0x180011c75  mov     esi, 80070057h
0x180011c7a  jmp     short loc_180011CBC
0x180011c7c  mov     rcx, rdi; unsigned __int16 *
0x180011c7f  xor     esi, esi
0x180011c81  call    ?IsChannelRegistered@CEventLogChannel@@SAJPEBG@Z; CEventLogChannel::IsChannelRegistered(ushort const *)
0x180011c86  test    eax, eax
0x180011c88  js      short loc_180011C92
0x180011c8a  mov     dword ptr [rbx], 1
0x180011c90  jmp     short loc_180011CBC
0x180011c92  mov     rcx, rdi; unsigned __int16 *
0x180011c95  call    ?IsCollectorRegistered@CEtwLogCollector@@SAJPEBG@Z; CEtwLogCollector::IsCollectorRegistered(ushort const *)
0x180011c9a  test    eax, eax
0x180011c9c  js      short loc_180011CA2
0x180011c9e  mov     [rbx], esi
0x180011ca0  jmp     short loc_180011CBC
0x180011ca2  mov     rdx, rdi
0x180011ca5  lea     rcx, aMdmconfigurati; "MdmConfiguration"
0x180011cac  call    cs:__imp__o__wcsicmp
0x180011cb2  test    eax, eax
0x180011cb4  jnz     short loc_180011CBC
0x180011cb6  mov     dword ptr [rbx], 2
0x180011cbc  mov     rbx, [rsp+28h+arg_0]
0x180011cc1  mov     eax, esi
0x180011cc3  mov     rsi, [rsp+28h+arg_8]
0x180011cc8  add     rsp, 20h
0x180011ccc  pop     rdi
0x180011ccd  retn
```
