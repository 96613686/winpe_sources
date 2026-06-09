# MpGetRequestorProcessId

- ea: `0x140003af0`
- end: `0x140003b4e`
- name: `MpGetRequestorProcessId`
- size: `94`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001550`
- `0x14002d520`
- `0x14002e850`
- `0x140055520`
- `0x140055eb0`
- `0x14006f0d8`
- `0x1400740f0`
- `0x140084340`

## callees

- `0x140003af0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140003b28`
- `ntoskrnl!PsGetProcessId` at `0x140003b28`
- `ntoskrnl!PsInitialSystemProcess` at `0x140003b1e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140003b39`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140003b39`
- `FLTMGR!FltGetRequestorProcessIdEx` at `0x140003af6`
- `FLTMGR!FltGetRequestorProcessIdEx` at `0x140003af6`

## pseudocode

```c
__int64 __fastcall MpGetRequestorProcessId(struct _FLT_CALLBACK_DATA *a1)
{
  HANDLE RequestorProcessId; // rbx
  HANDLE CurrentProcessId; // rax

  RequestorProcessId = FltGetRequestorProcessIdEx(a1);
  if ( *(_DWORD *)(MpData + 4076) )
  {
    if ( RequestorProcessId == PsGetProcessId(PsInitialSystemProcess) )
    {
      CurrentProcessId = PsGetCurrentProcessId();
      if ( CurrentProcessId != RequestorProcessId )
        LODWORD(RequestorProcessId) = (_DWORD)CurrentProcessId;
    }
  }
  return (unsigned int)RequestorProcessId;
}

```

## disassembly

```asm
0x140003af0  push    rbx
0x140003af2  sub     rsp, 20h
0x140003af6  call    cs:__imp_FltGetRequestorProcessIdEx
0x140003afd  nop     dword ptr [rax+rax+00h]
0x140003b02  mov     rbx, rax
0x140003b05  mov     rax, cs:MpData
0x140003b0c  cmp     dword ptr [rax+0FECh], 0
0x140003b13  jnz     short loc_140003B1E
0x140003b15  mov     eax, ebx
0x140003b17  add     rsp, 20h
0x140003b1b  pop     rbx
0x140003b1c  retn
0x140003b1e  mov     rcx, cs:__imp_PsInitialSystemProcess
0x140003b25  mov     rcx, [rcx]; Process
0x140003b28  call    cs:__imp_PsGetProcessId
0x140003b2f  nop     dword ptr [rax+rax+00h]
0x140003b34  cmp     rbx, rax
0x140003b37  jnz     short loc_140003B15
0x140003b39  call    cs:__imp_PsGetCurrentProcessId
0x140003b40  nop     dword ptr [rax+rax+00h]
0x140003b45  cmp     rax, rbx
0x140003b48  cmovnz  rbx, rax
0x140003b4c  jmp     short loc_140003B15
```
