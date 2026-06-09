# ContainerManager::FindContainer(_GUID,INgcCtnrContainer * *)

- ea: `0x180010350`
- end: `0x180010541`
- name: `?FindContainer@ContainerManager@@QEAAJU_GUID@@PEAPEAUINgcCtnrContainer@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct _GUID *, struct INgcCtnrContainer **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180010270`

## callees

- `0x180010350`
- `0x18002c640`
- `0x18002d4f4`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001038c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001038c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010424`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010507`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010424`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010507`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800104f3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800104f3`

## pseudocode

```c
__int64 __fastcall ContainerManager::FindContainer(RTL_SRWLOCK *this, struct _GUID *a2, struct INgcCtnrContainer **a3)
{
  RTL_SRWLOCK *v6; // rsi
  char *Ptr; // r14
  _BYTE *v8; // rbx
  char *v9; // rdi
  char v10; // cl
  _BYTE **v11; // rax
  struct INgcCtnrContainer *v12; // rbx
  _DWORD v14[2]; // [rsp+30h] [rbp-88h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-68h] BYREF
  void *v17; // [rsp+60h] [rbp-58h]
  int v18; // [rsp+68h] [rbp-50h]
  int v19; // [rsp+6Ch] [rbp-4Ch]
  _DWORD *v20; // [rsp+70h] [rbp-48h]
  __int64 v21; // [rsp+78h] [rbp-40h]

  *a3 = 0;
  v6 = this + 5;
  AcquireSRWLockShared(this + 5);
  Ptr = (char *)this[6].Ptr;
  v8 = (_BYTE *)*((_QWORD *)Ptr + 1);
  HIDWORD(EventDescriptor.Keyword) = 0;
  v9 = Ptr;
  if ( !v8[25] )
  {
    do
    {
      if ( memcmp_0(v8 + 32, a2, 0x10u) >= 0 )
      {
        v10 = 0;
        v9 = v8;
      }
      else
      {
        v10 = 1;
      }
      v11 = (_BYTE **)(v8 + 16);
      if ( !v10 )
        v11 = (_BYTE **)v8;
      v8 = *v11;
    }
    while ( !(*v11)[25] );
  }
  if ( v9[25] || memcmp_0(a2, v9 + 32, 0x10u) < 0 || v9 == Ptr )
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v14[0] = -2147023728;
      v20 = v14;
      v21 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_1800BE0C0;
      UserData.Size = *(unsigned __int16 *)off_1800BE0C0;
      UserData.Reserved = 2;
      v17 = &unk_1800A70A0;
      v18 = 47;
      v19 = 1;
      v14[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    if ( v6 )
      ReleaseSRWLockShared(v6);
    return 2147943568LL;
  }
  else
  {
    v12 = (struct INgcCtnrContainer *)*((_QWORD *)v9 + 6);
    if ( v12 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 8LL))(*((_QWORD *)v9 + 6));
    if ( v6 )
      ReleaseSRWLockShared(v6);
    *a3 = v12;
    return 0;
  }
}

```

## disassembly

```asm
0x180010350  mov     [rsp+arg_8], rbx
0x180010355  push    rbp
0x180010356  push    rsi
0x180010357  push    rdi
0x180010358  push    r14
0x18001035a  push    r15
0x18001035c  sub     rsp, 90h
0x180010363  mov     rax, cs:__security_cookie
0x18001036a  xor     rax, rsp
0x18001036d  mov     [rsp+0B8h+var_38], rax
0x180010375  mov     r15, r8
0x180010378  mov     rbp, rdx
0x18001037b  mov     rbx, rcx
0x18001037e  mov     qword ptr [r8], 0
0x180010385  lea     rsi, [rcx+28h]
0x180010389  mov     rcx, rsi; SRWLock
0x18001038c  call    cs:__imp_AcquireSRWLockShared
0x180010393  nop     dword ptr [rax+rax+00h]
0x180010398  mov     r14, [rbx+30h]
0x18001039c  mov     rbx, [r14+8]
0x1800103a0  xor     eax, eax
0x1800103a2  mov     dword ptr [rsp+0B8h+EventDescriptor.Keyword+4], eax
0x1800103a6  mov     rdi, r14
0x1800103a9  cmp     [rbx+19h], al
0x1800103ac  jnz     short loc_1800103E2
0x1800103ae  xchg    ax, ax
0x1800103b0  lea     rcx, [rbx+20h]; Buf1
0x1800103b4  mov     r8d, 10h; Size
0x1800103ba  mov     rdx, rbp; Buf2
0x1800103bd  call    memcmp_0
0x1800103c2  test    eax, eax
0x1800103c4  jns     short loc_1800103CA
0x1800103c6  mov     cl, 1
0x1800103c8  jmp     short loc_1800103CF
0x1800103ca  xor     cl, cl
0x1800103cc  mov     rdi, rbx
0x1800103cf  lea     rax, [rbx+10h]
0x1800103d3  test    cl, cl
0x1800103d5  cmovz   rax, rbx
0x1800103d9  mov     rbx, [rax]
0x1800103dc  cmp     byte ptr [rbx+19h], 0
0x1800103e0  jz      short loc_1800103B0
0x1800103e2  cmp     byte ptr [rdi+19h], 0
0x1800103e6  jnz     short loc_18001043A
0x1800103e8  lea     rdx, [rdi+20h]; Buf2
0x1800103ec  mov     r8d, 10h; Size
0x1800103f2  mov     rcx, rbp; Buf1
0x1800103f5  call    memcmp_0
0x1800103fa  test    eax, eax
0x1800103fc  js      short loc_18001043A
0x1800103fe  cmp     rdi, r14
0x180010401  jz      short loc_18001043A
0x180010403  mov     rbx, [rdi+30h]
0x180010407  test    rbx, rbx
0x18001040a  jz      short loc_18001041C
0x18001040c  mov     rax, [rbx]
0x18001040f  mov     rcx, rbx
0x180010412  mov     rax, [rax+8]
0x180010416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001041b  nop
0x18001041c  test    rsi, rsi
0x18001041f  jz      short loc_180010430
0x180010421  mov     rcx, rsi; SRWLock
0x180010424  call    cs:__imp_ReleaseSRWLockShared
0x18001042b  nop     dword ptr [rax+rax+00h]
0x180010430  mov     [r15], rbx
0x180010433  xor     eax, eax
0x180010435  jmp     loc_180010519
0x18001043a  mov     eax, cs:dword_1800BE0B8
0x180010440  cmp     eax, 2
0x180010443  jbe     loc_1800104FF
0x180010449  mov     [rsp+0B8h+var_88], 80070490h
0x180010451  lea     rax, [rsp+0B8h+var_88]
0x180010456  mov     [rsp+0B8h+var_48], rax
0x18001045b  mov     [rsp+0B8h+var_40], 4
0x180010464  mov     dword ptr [rsp+0B8h+EventDescriptor.Id], 0B000000h
0x18001046c  movzx   eax, cs:word_1800A7096
0x180010473  mov     dword ptr [rsp+0B8h+EventDescriptor.Level], eax
0x180010477  mov     qword ptr [rsp+40h], 0
0x180010480  mov     rax, cs:off_1800BE0C0
0x180010487  mov     [rsp+0B8h+var_68.Ptr], rax
0x18001048c  movzx   eax, word ptr [rax]
0x18001048f  mov     [rsp+0B8h+var_68.Size], eax
0x180010493  mov     dword ptr [rsp+0B8h+var_68.0Ch], 2
0x18001049b  lea     rax, unk_1800A70A0
0x1800104a2  mov     [rsp+0B8h+var_58], rax
0x1800104a7  mov     [rsp+0B8h+var_50], 2Fh ; '/'
0x1800104af  mov     [rsp+0B8h+var_4C], 1
0x1800104b7  lea     rax, _TraceLoggingMetadataEnd
0x1800104be  lea     rcx, _TraceLoggingMetadata
0x1800104c5  sub     eax, ecx
0x1800104c7  mov     [rsp+0B8h+var_84], eax
0x1800104cb  mov     eax, [rsp+0B8h+var_84]
0x1800104cf  lea     rax, [rsp+0B8h+var_68]
0x1800104d4  mov     [rsp+0B8h+UserData], rax; UserData
0x1800104d9  mov     [rsp+0B8h+UserDataCount], 3; UserDataCount
0x1800104e1  xor     r9d, r9d; RelatedActivityId
0x1800104e4  xor     r8d, r8d; ActivityId
0x1800104e7  lea     rdx, [rsp+0B8h+EventDescriptor]; EventDescriptor
0x1800104ec  mov     rcx, cs:RegHandle; RegHandle
0x1800104f3  call    cs:__imp_EventWriteTransfer
0x1800104fa  nop     dword ptr [rax+rax+00h]
0x1800104ff  test    rsi, rsi
0x180010502  jz      short loc_180010514
0x180010504  mov     rcx, rsi; SRWLock
0x180010507  call    cs:__imp_ReleaseSRWLockShared
0x18001050e  nop     dword ptr [rax+rax+00h]
0x180010513  nop
0x180010514  mov     eax, 80070490h
0x180010519  mov     rcx, [rsp+0B8h+var_38]
0x180010521  xor     rcx, rsp; StackCookie
0x180010524  call    __security_check_cookie
0x180010529  mov     rbx, [rsp+0B8h+arg_8]
0x180010531  add     rsp, 90h
0x180010538  pop     r15
0x18001053a  pop     r14
0x18001053c  pop     rdi
0x18001053d  pop     rsi
0x18001053e  pop     rbp
0x18001053f  retn
```
