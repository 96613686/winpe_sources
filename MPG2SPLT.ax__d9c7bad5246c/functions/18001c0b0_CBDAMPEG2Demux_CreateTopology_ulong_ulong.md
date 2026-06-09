# CBDAMPEG2Demux::CreateTopology(ulong,ulong)

- ea: `0x18001c0b0`
- end: `0x18001c1a3`
- name: `?CreateTopology@CBDAMPEG2Demux@@UEAAJKK@Z`
- size: `243`
- prototype: `__int64 __fastcall(CBDAMPEG2Demux *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180001460`
- `0x180001f04`
- `0x180014998`
- `0x18001c0b0`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001c136`
- `KERNEL32!LeaveCriticalSection` at `0x18001c136`
- `KERNEL32!EnterCriticalSection` at `0x18001c0eb`
- `KERNEL32!EnterCriticalSection` at `0x18001c0eb`

## pseudocode

```c
__int64 __fastcall CBDAMPEG2Demux::CreateTopology(CBDAMPEG2Demux *this, int a2, unsigned int a3)
{
  int PinRecordLocked; // edi
  void **v7; // rbx
  struct DEMUX_PIN_RECORD *v8; // [rsp+20h] [rbp-68h] BYREF
  wchar_t Buffer[32]; // [rsp+30h] [rbp-58h] BYREF

  if ( a2 )
    return 2147500037LL;
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 1) + 224LL));
  v8 = 0;
  swprintf_s(Buffer, 0x20u, L"%03d", a3);
  PinRecordLocked = CMPEG2Demultiplexer::FindPinRecordLocked_(*((CMPEG2Demultiplexer **)this + 1), Buffer, &v8, 0);
  LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this + 1) + 224LL));
  if ( PinRecordLocked >= 0 )
  {
    v7 = (void **)v8;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( v7 )
      {
        operator delete(v7[2]);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*v7 + 1) + 16LL))(*((_QWORD *)*v7 + 1));
        operator delete(v7);
      }
    }
  }
  return (unsigned int)PinRecordLocked;
}

```

## disassembly

```asm
0x18001c0b0  mov     [rsp+arg_8], rbx
0x18001c0b5  push    rdi
0x18001c0b6  sub     rsp, 80h
0x18001c0bd  mov     rax, cs:__security_cookie
0x18001c0c4  xor     rax, rsp
0x18001c0c7  mov     [rsp+88h+var_18], rax
0x18001c0cc  mov     edi, r8d
0x18001c0cf  mov     rbx, rcx
0x18001c0d2  test    edx, edx
0x18001c0d4  jz      short loc_18001C0E0
0x18001c0d6  mov     eax, 80004005h
0x18001c0db  jmp     loc_18001C185
0x18001c0e0  mov     rcx, [rcx+8]
0x18001c0e4  add     rcx, 0E0h; lpCriticalSection
0x18001c0eb  call    cs:__imp_EnterCriticalSection
0x18001c0f1  mov     r9d, edi
0x18001c0f4  mov     [rsp+88h+var_68], 0
0x18001c0fd  lea     r8, a03d; "%03d"
0x18001c104  mov     edx, 20h ; ' '; BufferCount
0x18001c109  lea     rcx, [rsp+88h+Buffer]; Buffer
0x18001c10e  call    swprintf_s
0x18001c113  mov     rcx, [rbx+8]; this
0x18001c117  lea     r8, [rsp+88h+var_68]; struct DEMUX_PIN_RECORD **
0x18001c11c  xor     r9d, r9d; unsigned int *
0x18001c11f  lea     rdx, [rsp+88h+Buffer]; unsigned __int16 *
0x18001c124  call    ?FindPinRecordLocked_@CMPEG2Demultiplexer@@AEAAJPEBGPEAPEAUDEMUX_PIN_RECORD@@PEAK@Z; CMPEG2Demultiplexer::FindPinRecordLocked_(ushort const *,DEMUX_PIN_RECORD * *,ulong *)
0x18001c129  mov     rcx, [rbx+8]
0x18001c12d  mov     edi, eax
0x18001c12f  add     rcx, 0E0h; lpCriticalSection
0x18001c136  call    cs:__imp_LeaveCriticalSection
0x18001c13c  test    edi, edi
0x18001c13e  js      short loc_18001C183
0x18001c140  mov     rbx, [rsp+88h+var_68]
0x18001c145  or      ecx, 0FFFFFFFFh
0x18001c148  lock xadd [rbx+8], ecx
0x18001c14d  cmp     ecx, 1
0x18001c150  jnz     short loc_18001C183
0x18001c152  test    rbx, rbx
0x18001c155  jz      short loc_18001C183
0x18001c157  lea     edx, [rcx+1]; unsigned __int64
0x18001c15a  mov     rcx, [rbx+10h]; void *
0x18001c15e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c163  mov     rax, [rbx]
0x18001c166  mov     rcx, [rax+8]
0x18001c16a  mov     rax, [rcx]
0x18001c16d  mov     rax, [rax+10h]
0x18001c171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c176  mov     edx, 18h; unsigned __int64
0x18001c17b  mov     rcx, rbx; void *
0x18001c17e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c183  mov     eax, edi
0x18001c185  mov     rcx, [rsp+88h+var_18]
0x18001c18a  xor     rcx, rsp; StackCookie
0x18001c18d  call    __security_check_cookie
0x18001c192  mov     rbx, [rsp+88h+arg_8]
0x18001c19a  add     rsp, 80h
0x18001c1a1  pop     rdi
0x18001c1a2  retn
```
