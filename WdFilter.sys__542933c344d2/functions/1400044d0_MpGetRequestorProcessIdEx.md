# MpGetRequestorProcessIdEx

- ea: `0x1400044d0`
- end: `0x14000452f`
- name: `MpGetRequestorProcessIdEx`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14006e7d0`

## callees

- `0x1400044d0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140004509`
- `ntoskrnl!PsGetProcessId` at `0x140004509`
- `ntoskrnl!PsInitialSystemProcess` at `0x1400044ff`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000451a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14000451a`
- `FLTMGR!FltGetRequestorProcessIdEx` at `0x1400044d6`
- `FLTMGR!FltGetRequestorProcessIdEx` at `0x1400044d6`

## pseudocode

```c
HANDLE __fastcall MpGetRequestorProcessIdEx(struct _FLT_CALLBACK_DATA *a1)
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
        return CurrentProcessId;
    }
  }
  return RequestorProcessId;
}

```

## disassembly

```asm
0x1400044d0  push    rbx
0x1400044d2  sub     rsp, 20h
0x1400044d6  call    cs:__imp_FltGetRequestorProcessIdEx
0x1400044dd  nop     dword ptr [rax+rax+00h]
0x1400044e2  mov     rbx, rax
0x1400044e5  mov     rax, cs:MpData
0x1400044ec  cmp     dword ptr [rax+0FECh], 0
0x1400044f3  jnz     short loc_1400044FF
0x1400044f5  mov     rax, rbx
0x1400044f8  add     rsp, 20h
0x1400044fc  pop     rbx
0x1400044fd  retn
0x1400044ff  mov     rcx, cs:__imp_PsInitialSystemProcess
0x140004506  mov     rcx, [rcx]; Process
0x140004509  call    cs:__imp_PsGetProcessId
0x140004510  nop     dword ptr [rax+rax+00h]
0x140004515  cmp     rbx, rax
0x140004518  jnz     short loc_1400044F5
0x14000451a  call    cs:__imp_PsGetCurrentProcessId
0x140004521  nop     dword ptr [rax+rax+00h]
0x140004526  cmp     rax, rbx
0x140004529  cmovnz  rbx, rax
0x14000452d  jmp     short loc_1400044F5
```
