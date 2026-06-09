# CSCardSubcontext::CSCardSubcontext(void)

- ea: `0x180015b6c`
- end: `0x180015c4e`
- name: `??0CSCardSubcontext@@QEAA@XZ`
- size: `226`
- prototype: `CSCardSubcontext *__fastcall(CSCardSubcontext *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008f70`

## callees

- `0x180008f20`
- `0x180015b6c`
- `0x18001685c`
- `0x18002ef20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015bcd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c29`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
CSCardSubcontext *__fastcall CSCardSubcontext::CSCardSubcontext(CSCardSubcontext *this, unsigned int a2)
{
  CHandleObject *v3; // rdi
  char *EventW; // rsi
  DWORD LastError; // eax
  ulong pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  *(_QWORD *)this = &CSCardSubcontext::`vftable';
  v3 = (CSCardSubcontext *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  CCriticalSectionObject::CCriticalSectionObject((CSCardSubcontext *)((char *)this + 48), a2);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 2) = 1;
  EventW = (char *)CreateEventW(0, 1, 1, 0);
  if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    LastError = GetLastError();
  else
    LastError = 0;
  *((_DWORD *)v3 + 2) = LastError;
  if ( (unsigned __int64)(*(_QWORD *)v3 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close(v3);
  *(_QWORD *)v3 = EventW;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  if ( ((unsigned __int64)(EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    pExceptionObject = *((_DWORD *)this + 8);
    throw &pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180015b6c  mov     [rsp+arg_10], rbx
0x180015b71  mov     [rsp+arg_18], rsi
0x180015b76  mov     [rsp+arg_0], rcx
0x180015b7b  push    rdi
0x180015b7c  sub     rsp, 20h
0x180015b80  mov     rbx, rcx
0x180015b83  lea     rax, ??_7CSCardSubcontext@@6B@; const CSCardSubcontext::`vftable'
0x180015b8a  mov     [rcx], rax
0x180015b8d  lea     rdi, [rcx+18h]
0x180015b91  mov     qword ptr [rdi], 0
0x180015b98  mov     dword ptr [rdi+8], 0
0x180015b9f  add     rcx, 30h ; '0'; this
0x180015ba3  call    ??0CCriticalSectionObject@@QEAA@K@Z; CCriticalSectionObject::CCriticalSectionObject(ulong)
0x180015ba8  nop
0x180015ba9  mov     qword ptr [rbx+8], 0
0x180015bb1  mov     qword ptr [rbx+28h], 0
0x180015bb9  mov     qword ptr [rbx+10h], 1
0x180015bc1  xor     r9d, r9d; lpName
0x180015bc4  lea     edx, [r9+1]; bManualReset
0x180015bc8  xor     ecx, ecx; lpEventAttributes
0x180015bca  mov     r8d, edx; bInitialState
0x180015bcd  call    cs:__imp_CreateEventW
0x180015bd3  mov     rsi, rax
0x180015bd6  lea     rcx, [rax-1]
0x180015bda  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180015bde  ja      short loc_180015C29
0x180015be0  xor     eax, eax
0x180015be2  mov     [rdi+8], eax
0x180015be5  mov     rax, [rdi]
0x180015be8  dec     rax
0x180015beb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015bef  jbe     short loc_180015C31
0x180015bf1  mov     [rdi], rsi
0x180015bf4  mov     qword ptr [rbx+68h], 0
0x180015bfc  mov     qword ptr [rbx+70h], 0
0x180015c04  lea     rax, [rsi+1]
0x180015c08  test    rax, 0FFFFFFFFFFFFFFFEh
0x180015c0e  jnz     short loc_180015C3B
0x180015c10  mov     eax, [rbx+20h]
0x180015c13  mov     [rsp+28h+pExceptionObject], eax
0x180015c17  lea     rdx, _TI1K; pThrowInfo
0x180015c1e  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180015c23  call    _CxxThrowException_0
0x180015c29  call    cs:__imp_GetLastError
0x180015c2f  jmp     short loc_180015BE2
0x180015c31  mov     rcx, rdi; this
0x180015c34  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x180015c39  jmp     short loc_180015BF1
0x180015c3b  mov     rax, rbx
0x180015c3e  mov     rbx, [rsp+28h+arg_10]
0x180015c43  mov     rsi, [rsp+28h+arg_18]
0x180015c48  add     rsp, 20h
0x180015c4c  pop     rdi
0x180015c4d  retn
```
