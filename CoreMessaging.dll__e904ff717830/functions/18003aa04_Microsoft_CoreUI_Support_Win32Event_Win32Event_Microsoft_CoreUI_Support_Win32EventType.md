# Microsoft::CoreUI::Support::Win32Event::Win32Event(Microsoft::CoreUI::Support::Win32EventType)

- ea: `0x18003aa04`
- end: `0x18003aa6c`
- name: `??0Win32Event@Support@CoreUI@Microsoft@@QEAA@W4Win32EventType@123@@Z`
- size: `104`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180026628`
- `0x18004e780`
- `0x18008b768`
- `0x180091fbc`
- `0x18009a960`
- `0x18009cf54`
- `0x1800b7740`
- `0x1800b79d4`

## callees

- `0x180007d80`
- `0x18003950c`
- `0x18003aa04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003aa25`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003aa25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003aa45`

## pseudocode

```c
_QWORD *__fastcall Microsoft::CoreUI::Support::Win32Event::Win32Event(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  BOOL v5; // edx
  HANDLE EventW; // rax
  signed int LastError; // eax

  *a1 = 0;
  if ( (_DWORD)a2 )
  {
    if ( (_DWORD)a2 != 1 )
      CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
        a1,
        a2,
        a3,
        a4);
    v5 = 0;
  }
  else
  {
    v5 = 1;
  }
  EventW = CreateEventW(0, v5, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CFlat::Abandonment::FailWithHR(LastError, 0, 0);
  }
  *a1 = EventW;
  return a1;
}

```

## disassembly

```asm
0x18003aa04  push    rbx
0x18003aa06  sub     rsp, 20h
0x18003aa0a  mov     qword ptr [rcx], 0
0x18003aa11  mov     rbx, rcx
0x18003aa14  test    edx, edx
0x18003aa16  jnz     short loc_18003AA3C
0x18003aa18  mov     edx, 1; bManualReset
0x18003aa1d  xor     r9d, r9d; lpName
0x18003aa20  xor     r8d, r8d; bInitialState
0x18003aa23  xor     ecx, ecx; lpEventAttributes
0x18003aa25  call    cs:__imp_CreateEventW
0x18003aa2b  test    rax, rax
0x18003aa2e  jz      short loc_18003AA45
0x18003aa30  mov     [rbx], rax
0x18003aa33  mov     rax, rbx
0x18003aa36  add     rsp, 20h
0x18003aa3a  pop     rbx
0x18003aa3b  retn
0x18003aa3c  cmp     edx, 1
0x18003aa3f  jnz     short loc_18003AA5C
0x18003aa41  xor     edx, edx
0x18003aa43  jmp     short loc_18003AA1D
0x18003aa45  call    cs:__imp_GetLastError
0x18003aa4b  test    eax, eax
0x18003aa4d  jg      short loc_18003AA62
0x18003aa4f  xor     r8d, r8d; int
0x18003aa52  xor     edx, edx; void *
0x18003aa54  mov     ecx, eax; int
0x18003aa56  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x18003aa5c  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x18003aa62  movzx   eax, ax
0x18003aa65  or      eax, 80070000h
0x18003aa6a  jmp     short loc_18003AA4F
```
