# CMonitor::StartUp(void)

- ea: `0x18000ac44`
- end: `0x18000ad26`
- name: `?StartUp@CMonitor@@AEAA_NXZ`
- size: `226`
- prototype: `bool __fastcall(CMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a920`

## callees

- `0x18000ac44`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000ad0d`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad0d`
- `KERNEL32!EnterCriticalSection` at `0x18000ac5a`
- `KERNEL32!EnterCriticalSection` at `0x18000ac5a`
- `KERNEL32!CreateEventA` at `0x18000ac9f`
- `KERNEL32!CreateEventA` at `0x18000acba`
- `KERNEL32!CreateEventA` at `0x18000ac9f`
- `KERNEL32!CreateEventA` at `0x18000acba`
- `KERNEL32!CreateThread` at `0x18000acf3`
- `KERNEL32!CreateThread` at `0x18000acf3`
- `KERNEL32!SetEvent` at `0x18000ac80`
- `KERNEL32!SetEvent` at `0x18000ac80`

## pseudocode

```c
char __fastcall CMonitor::StartUp(CMonitor *this)
{
  char v2; // di
  HANDLE v3; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_BYTE *)this + 113) )
  {
    v2 = 0;
  }
  else if ( *((_BYTE *)this + 112) )
  {
    SetEvent(*((HANDLE *)this + 11));
    v2 = 1;
  }
  else
  {
    v2 = 0;
    if ( !*((_QWORD *)this + 11) )
      *((_QWORD *)this + 11) = CreateEventA(0, 0, 0, 0);
    if ( !*((_QWORD *)this + 12) )
      *((_QWORD *)this + 12) = CreateEventA(0, 0, 0, 0);
    if ( *((_QWORD *)this + 11) )
    {
      ThreadId = 0;
      v3 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CMonitor::ThreadFunc, this, 0, &ThreadId);
      *((_QWORD *)this + 13) = v3;
      if ( v3 )
      {
        v2 = 1;
        *((_BYTE *)this + 112) = 1;
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return v2;
}

```

## disassembly

```asm
0x18000ac44  mov     [rsp+arg_8], rbx
0x18000ac49  mov     [rsp+arg_10], rsi
0x18000ac4e  push    rdi
0x18000ac4f  sub     rsp, 30h
0x18000ac53  mov     rbx, rcx
0x18000ac56  add     rcx, 30h ; '0'; lpCriticalSection
0x18000ac5a  call    cs:__imp_EnterCriticalSection
0x18000ac60  mov     al, [rbx+70h]
0x18000ac63  mov     al, [rbx+71h]
0x18000ac66  mov     al, [rbx+71h]
0x18000ac69  test    al, al
0x18000ac6b  jz      short loc_18000AC75
0x18000ac6d  xor     dil, dil
0x18000ac70  jmp     loc_18000AD09
0x18000ac75  mov     al, [rbx+70h]
0x18000ac78  test    al, al
0x18000ac7a  jz      short loc_18000AC8B
0x18000ac7c  mov     rcx, [rbx+58h]; hEvent
0x18000ac80  call    cs:__imp_SetEvent
0x18000ac86  mov     dil, 1
0x18000ac89  jmp     short loc_18000AD09
0x18000ac8b  xor     dil, dil
0x18000ac8e  cmp     qword ptr [rbx+58h], 0
0x18000ac93  jnz     short loc_18000ACA9
0x18000ac95  xor     r9d, r9d; lpName
0x18000ac98  xor     r8d, r8d; bInitialState
0x18000ac9b  xor     edx, edx; bManualReset
0x18000ac9d  xor     ecx, ecx; lpEventAttributes
0x18000ac9f  call    cs:__imp_CreateEventA
0x18000aca5  mov     [rbx+58h], rax
0x18000aca9  cmp     qword ptr [rbx+60h], 0
0x18000acae  jnz     short loc_18000ACC4
0x18000acb0  xor     r9d, r9d; lpName
0x18000acb3  xor     r8d, r8d; bInitialState
0x18000acb6  xor     edx, edx; bManualReset
0x18000acb8  xor     ecx, ecx; lpEventAttributes
0x18000acba  call    cs:__imp_CreateEventA
0x18000acc0  mov     [rbx+60h], rax
0x18000acc4  cmp     qword ptr [rbx+58h], 0
0x18000acc9  jz      short loc_18000AD09
0x18000accb  lea     rax, [rsp+38h+ThreadId]
0x18000acd0  mov     [rsp+38h+ThreadId], 0
0x18000acd8  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000acdd  lea     r8, ?ThreadFunc@CMonitor@@CAIPEAX@Z; lpStartAddress
0x18000ace4  mov     r9, rbx; lpParameter
0x18000ace7  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18000acef  xor     edx, edx; dwStackSize
0x18000acf1  xor     ecx, ecx; lpThreadAttributes
0x18000acf3  call    cs:__imp_CreateThread
0x18000acf9  mov     [rbx+68h], rax
0x18000acfd  test    rax, rax
0x18000ad00  jz      short loc_18000AD09
0x18000ad02  mov     dil, 1
0x18000ad05  mov     [rbx+70h], dil
0x18000ad09  lea     rcx, [rbx+30h]; lpCriticalSection
0x18000ad0d  call    cs:__imp_LeaveCriticalSection
0x18000ad13  mov     rbx, [rsp+38h+arg_8]
0x18000ad18  mov     al, dil
0x18000ad1b  mov     rsi, [rsp+38h+arg_10]
0x18000ad20  add     rsp, 30h
0x18000ad24  pop     rdi
0x18000ad25  retn
```
