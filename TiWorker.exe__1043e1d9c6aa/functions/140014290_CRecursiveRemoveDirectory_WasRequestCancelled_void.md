# CRecursiveRemoveDirectory::WasRequestCancelled(void)

- ea: `0x140014290`
- end: `0x1400142fc`
- name: `?WasRequestCancelled@CRecursiveRemoveDirectory@@AEAA_NXZ`
- size: `108`
- prototype: `bool __fastcall(CRecursiveRemoveDirectory *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140012c58`

## callees

- `0x14000e034`
- `0x14000e150`
- `0x140014290`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400142aa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400142aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400142bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400142bc`

## string_xrefs

- `0x1400142de`: `Remove directory cancelled`

## pseudocode

```c
bool __fastcall CRecursiveRemoveDirectory::WasRequestCancelled(CRecursiveRemoveDirectory *this)
{
  void *v2; // rcx
  DWORD v3; // eax
  signed int LastError; // eax
  __int64 v5; // rcx

  if ( !*((_BYTE *)this + 32) )
  {
    v2 = (void *)*((_QWORD *)this + 3);
    if ( v2 )
    {
      v3 = WaitForSingleObject(v2, 0);
      if ( (v3 & 0xFFFFFF7F) != 0 )
      {
        if ( v3 == -1 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          LogAdapter::TraceAtLevelIfFailed<long,>(v5, (unsigned int)LastError, "Error getting cancel event status");
        }
      }
      else
      {
        LogAdapter::TraceAtLevel<>(1, (struct Windows::Rtl::IRtlFormattedOutputStream *)"Remove directory cancelled");
        *((_BYTE *)this + 32) = 1;
      }
    }
  }
  return *((_BYTE *)this + 32);
}

```

## disassembly

```asm
0x140014290  push    rbx
0x140014292  sub     rsp, 20h
0x140014296  cmp     byte ptr [rcx+20h], 0
0x14001429a  mov     rbx, rcx
0x14001429d  jnz     short loc_1400142F3
0x14001429f  mov     rcx, [rcx+18h]; hHandle
0x1400142a3  test    rcx, rcx
0x1400142a6  jz      short loc_1400142F3
0x1400142a8  xor     edx, edx; dwMilliseconds
0x1400142aa  call    cs:__imp_WaitForSingleObject
0x1400142b0  test    eax, 0FFFFFF7Fh
0x1400142b5  jz      short loc_1400142DE
0x1400142b7  cmp     eax, 0FFFFFFFFh
0x1400142ba  jnz     short loc_1400142F3
0x1400142bc  call    cs:__imp_GetLastError
0x1400142c2  test    eax, eax
0x1400142c4  jle     short loc_1400142CE
0x1400142c6  movzx   eax, ax
0x1400142c9  or      eax, 80070000h
0x1400142ce  lea     r8, aErrorGettingCa; "Error getting cancel event status"
0x1400142d5  mov     edx, eax
0x1400142d7  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1400142dc  jmp     short loc_1400142F3
0x1400142de  lea     rdx, aRemoveDirector; "Remove directory cancelled"
0x1400142e5  mov     ecx, 1
0x1400142ea  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1400142ef  mov     byte ptr [rbx+20h], 1
0x1400142f3  mov     al, [rbx+20h]
0x1400142f6  add     rsp, 20h
0x1400142fa  pop     rbx
0x1400142fb  retn
```
