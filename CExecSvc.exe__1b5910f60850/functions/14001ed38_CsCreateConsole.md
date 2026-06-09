# CsCreateConsole

- ea: `0x14001ed38`
- end: `0x14001ef69`
- name: `CsCreateConsole`
- size: `561`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001b5ec`

## callees

- `0x14001ed38`
- `0x14001ef70`
- `0x14001f40c`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x14001ee57`
- `ntdll!NtCreateEvent` at `0x14001ee57`
- `ntdll!RtlAllocateHeap` at `0x14001ed81`
- `ntdll!RtlAllocateHeap` at `0x14001ed81`
- `ntdll!RtlFreeHeap` at `0x14001ee75`
- `ntdll!RtlFreeHeap` at `0x14001ef4f`
- `ntdll!RtlFreeHeap` at `0x14001ee75`
- `ntdll!RtlFreeHeap` at `0x14001ef4f`
- `ntdll!RtlInitializeSRWLock` at `0x14001ee08`
- `ntdll!RtlInitializeSRWLock` at `0x14001ee12`
- `ntdll!RtlInitializeSRWLock` at `0x14001ee08`
- `ntdll!RtlInitializeSRWLock` at `0x14001ee12`
- `ntdll!TpAllocIoCompletion` at `0x14001ef20`
- `ntdll!TpAllocIoCompletion` at `0x14001ef20`
- `ntdll!NtDeviceIoControlFile` at `0x14001eed0`
- `ntdll!NtDeviceIoControlFile` at `0x14001eed0`
- `ntdll!NtClose` at `0x14001eedf`
- `ntdll!NtClose` at `0x14001ef37`
- `ntdll!NtClose` at `0x14001eedf`
- `ntdll!NtClose` at `0x14001ef37`

## pseudocode

```c
__int64 __fastcall CsCreateConsole(
        void ***a1,
        void *a2,
        __int64 a3,
        __int16 a4,
        __int16 a5,
        __int16 a6,
        __int16 a7,
        HANDLE InputBuffer)
{
  _QWORD *Heap; // rax
  void **v13; // rdi
  _QWORD *v15; // rbx
  HANDLE *v16; // rbx
  NTSTATUS Event; // esi
  void *v18; // rsi
  void *v19; // rdx
  int v20; // ebp
  void *v21; // [rsp+50h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-40h] BYREF

  InputBuffer = 0;
  v21 = 0;
  IoStatusBlock = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x998u);
  v13 = (void **)Heap;
  if ( !Heap )
    return 3221225626LL;
  *((_WORD *)Heap + 20) = a4;
  *Heap = a2;
  v15 = Heap + 23;
  *((_WORD *)Heap + 21) = a5;
  *((_WORD *)Heap + 22) = a6;
  *((_WORD *)Heap + 23) = a7;
  Heap[4] = &ConsoleToPipeRedirector::Callbacks;
  *((_BYTE *)Heap + 56) = 0;
  Heap[2] = a3;
  Heap[17] = 0;
  *((_DWORD *)Heap + 36) = 0;
  *((_DWORD *)Heap + 33) = 7;
  Heap[22] = Heap + 23;
  RtlInitializeSRWLock(Heap + 13);
  RtlInitializeSRWLock(v13 + 6);
  v13[24] = v13 + 23;
  v13[9] = v13 + 8;
  v13[8] = v13 + 8;
  *v15 = v15;
  v13[11] = v13 + 10;
  v16 = v13 + 1;
  v13[10] = v13 + 10;
  v13[15] = v13 + 14;
  v13[14] = v13 + 14;
  Event = NtCreateEvent(v13 + 1, 0x100002u, 0, NotificationEvent, 0);
  if ( Event < 0 )
    goto LABEL_4;
  InputBuffer = *v16;
  Event = NtDeviceIoControlFile(a2, 0, 0, 0, &IoStatusBlock, 0x50001Fu, &InputBuffer, 8u, 0, 0);
  if ( Event < 0 || (Event = CspAllocateServerScreen(&v21, v13), Event < 0) )
  {
    NtClose(*v16);
LABEL_4:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    return (unsigned int)Event;
  }
  v18 = v21;
  v19 = *v13;
  v13[12] = v21;
  v20 = TpAllocIoCompletion(v13 + 3, v19, CspConsoleIoRead, v13, 0);
  if ( v20 >= 0 )
  {
    *a1 = v13;
    return 0;
  }
  else
  {
    CspFreeServerScreen(v18);
    NtClose(*v16);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    return (unsigned int)v20;
  }
}

```

## disassembly

```asm
0x14001ed38  mov     rax, rsp
0x14001ed3b  push    rbx
0x14001ed3c  push    rbp
0x14001ed3d  push    rsi
0x14001ed3e  push    rdi
0x14001ed3f  push    r14
0x14001ed41  sub     rsp, 70h
0x14001ed45  mov     r14, rcx
0x14001ed48  mov     qword ptr [rax+40h], 0
0x14001ed50  xorps   xmm0, xmm0
0x14001ed53  mov     qword ptr [rax-48h], 0
0x14001ed5b  movups  xmmword ptr [rax-40h], xmm0
0x14001ed5f  mov     rcx, gs:60h
0x14001ed68  mov     rsi, r8
0x14001ed6b  mov     rbp, rdx
0x14001ed6e  mov     r8d, 998h; Size
0x14001ed74  mov     edx, 8; Flags
0x14001ed79  movzx   ebx, r9w
0x14001ed7d  mov     rcx, [rcx+30h]; HeapHandle
0x14001ed81  call    cs:__imp_RtlAllocateHeap
0x14001ed87  mov     rdi, rax
0x14001ed8a  test    rax, rax
0x14001ed8d  jnz     short loc_14001ED99
0x14001ed8f  mov     eax, 0C000009Ah
0x14001ed94  jmp     loc_14001EF5E
0x14001ed99  mov     [rax+28h], bx
0x14001ed9d  lea     rcx, [rdi+68h]
0x14001eda1  mov     [rax], rbp
0x14001eda4  lea     rbx, [rdi+0B8h]
0x14001edab  movzx   eax, [rsp+98h+arg_20]
0x14001edb3  mov     [rdi+2Ah], ax
0x14001edb7  movzx   eax, [rsp+98h+arg_28]
0x14001edbf  mov     [rdi+2Ch], ax
0x14001edc3  movzx   eax, [rsp+98h+arg_30]
0x14001edcb  mov     [rdi+2Eh], ax
0x14001edcf  lea     rax, ?Callbacks@ConsoleToPipeRedirector@@0U_CS_CONSOLE_CALLBACK@@B; _CS_CONSOLE_CALLBACK const ConsoleToPipeRedirector::Callbacks
0x14001edd6  mov     [rdi+20h], rax
0x14001edda  mov     byte ptr [rdi+38h], 0
0x14001edde  mov     [rdi+10h], rsi
0x14001ede2  mov     qword ptr [rdi+88h], 0
0x14001eded  mov     dword ptr [rdi+90h], 0
0x14001edf7  mov     dword ptr [rdi+84h], 7
0x14001ee01  mov     [rdi+0B0h], rbx
0x14001ee08  call    cs:__imp_RtlInitializeSRWLock
0x14001ee0e  lea     rcx, [rdi+30h]
0x14001ee12  call    cs:__imp_RtlInitializeSRWLock
0x14001ee18  lea     rax, [rdi+40h]
0x14001ee1c  mov     [rbx+8], rbx
0x14001ee20  mov     [rax+8], rax
0x14001ee24  xor     r9d, r9d; EventType
0x14001ee27  mov     [rax], rax
0x14001ee2a  xor     r8d, r8d; ObjectAttributes
0x14001ee2d  lea     rax, [rdi+50h]
0x14001ee31  mov     [rbx], rbx
0x14001ee34  mov     [rax+8], rax
0x14001ee38  lea     rbx, [rdi+8]
0x14001ee3c  mov     [rax], rax
0x14001ee3f  mov     edx, 100002h; DesiredAccess
0x14001ee44  lea     rax, [rdi+70h]
0x14001ee48  mov     [rsp+98h+InitialState], 0; InitialState
0x14001ee4d  mov     rcx, rbx; EventHandle
0x14001ee50  mov     [rax+8], rax
0x14001ee54  mov     [rax], rax
0x14001ee57  call    cs:__imp_NtCreateEvent
0x14001ee5d  mov     esi, eax
0x14001ee5f  test    eax, eax
0x14001ee61  jns     short loc_14001EE82
0x14001ee63  mov     rcx, gs:60h
0x14001ee6c  mov     r8, rdi; P
0x14001ee6f  xor     edx, edx; Flags
0x14001ee71  mov     rcx, [rcx+30h]; HeapHandle
0x14001ee75  call    cs:__imp_RtlFreeHeap
0x14001ee7b  mov     eax, esi
0x14001ee7d  jmp     loc_14001EF5E
0x14001ee82  mov     rax, [rbx]
0x14001ee85  xor     r9d, r9d; ApcContext
0x14001ee88  mov     [rsp+98h+OutputBufferLength], 0; OutputBufferLength
0x14001ee90  xor     r8d, r8d; ApcRoutine
0x14001ee93  mov     [rsp+98h+OutputBuffer], 0; OutputBuffer
0x14001ee9c  xor     edx, edx; Event
0x14001ee9e  mov     [rsp+98h+arg_38], rax
0x14001eea6  mov     rcx, rbp; FileHandle
0x14001eea9  mov     [rsp+98h+InputBufferLength], 8; InputBufferLength
0x14001eeb1  lea     rax, [rsp+98h+arg_38]
0x14001eeb9  mov     [rsp+98h+InputBuffer], rax; InputBuffer
0x14001eebe  lea     rax, [rsp+98h+IoStatusBlock]
0x14001eec3  mov     [rsp+98h+IoControlCode], 50001Fh; IoControlCode
0x14001eecb  mov     qword ptr [rsp+98h+InitialState], rax; IoStatusBlock
0x14001eed0  call    cs:__imp_NtDeviceIoControlFile
0x14001eed6  mov     esi, eax
0x14001eed8  test    eax, eax
0x14001eeda  jns     short loc_14001EEEA
0x14001eedc  mov     rcx, [rbx]; Handle
0x14001eedf  call    cs:__imp_NtClose
0x14001eee5  jmp     loc_14001EE63
0x14001eeea  mov     rdx, rdi
0x14001eeed  lea     rcx, [rsp+98h+var_48]
0x14001eef2  call    CspAllocateServerScreen
0x14001eef7  mov     esi, eax
0x14001eef9  test    eax, eax
0x14001eefb  js      short loc_14001EEDC
0x14001eefd  mov     rsi, [rsp+98h+var_48]
0x14001ef02  lea     rcx, [rdi+18h]
0x14001ef06  mov     rdx, [rdi]
0x14001ef09  lea     r8, CspConsoleIoRead
0x14001ef10  mov     r9, rdi
0x14001ef13  mov     [rdi+60h], rsi
0x14001ef17  mov     qword ptr [rsp+98h+InitialState], 0
0x14001ef20  call    cs:__imp_TpAllocIoCompletion
0x14001ef26  mov     ebp, eax
0x14001ef28  test    eax, eax
0x14001ef2a  jns     short loc_14001EF59
0x14001ef2c  mov     rcx, rsi
0x14001ef2f  call    CspFreeServerScreen
0x14001ef34  mov     rcx, [rbx]; Handle
0x14001ef37  call    cs:__imp_NtClose
0x14001ef3d  mov     rcx, gs:60h
0x14001ef46  mov     r8, rdi; P
0x14001ef49  xor     edx, edx; Flags
0x14001ef4b  mov     rcx, [rcx+30h]; HeapHandle
0x14001ef4f  call    cs:__imp_RtlFreeHeap
0x14001ef55  mov     eax, ebp
0x14001ef57  jmp     short loc_14001EF5E
0x14001ef59  mov     [r14], rdi
0x14001ef5c  xor     eax, eax
0x14001ef5e  add     rsp, 70h
0x14001ef62  pop     r14
0x14001ef64  pop     rdi
0x14001ef65  pop     rsi
0x14001ef66  pop     rbp
0x14001ef67  pop     rbx
0x14001ef68  retn
```
