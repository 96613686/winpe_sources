# GameInputDevice::ReplaceBuffer(ISIPCEndpoint *,unsigned __int64,void *,void const *)

- ea: `0x18000a91c`
- end: `0x18000aa8f`
- name: `?ReplaceBuffer@GameInputDevice@@QEAAJPEAUISIPCEndpoint@@_KPEAXPEBX@Z`
- size: `371`
- prototype: `__int64 __fastcall(GameInputDevice *this, struct ISIPCEndpoint *, unsigned __int64, void *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180004c30`
- `0x180009050`

## callees

- `0x18000120c`
- `0x180005200`
- `0x180008550`
- `0x18000a7d0`
- `0x18000a91c`
- `0x18000bd8c`
- `0x18000d68c`

## pseudocode

```c
__int64 __fastcall GameInputDevice::ReplaceBuffer(
        GameInputDevice *this,
        struct ISIPCEndpoint *a2,
        unsigned __int64 a3,
        void *a4,
        void *a5)
{
  char *v9; // r15
  int v10; // edi
  int v11; // r8d
  int v12; // r9d
  _QWORD *v13; // rcx
  _QWORD *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rcx
  FeedbackStateCache *v17; // rcx
  __int16 v19; // [rsp+50h] [rbp-28h] BYREF
  __int16 v20; // [rsp+52h] [rbp-26h] BYREF
  struct SharedBuffer *v21; // [rsp+58h] [rbp-20h] BYREF
  const char *v22; // [rsp+60h] [rbp-18h] BYREF
  const char *v23; // [rsp+68h] [rbp-10h] BYREF

  if ( !GameInputDispatcher::IsDispatchThread() )
  {
    GameInputFailFast(2147549183LL, 160);
    JUMPOUT(0x18000AA8ELL);
  }
  v21 = 0;
  v9 = (char *)this + 32;
  v10 = SharedBuffer::Create(this, a2, a3, a4, (struct GameInputDeviceInfo **)this + 4, &v21);
  if ( v10 < 0 )
  {
    GameInputDevice::RemoveBuffer(this, a5);
  }
  else
  {
    v13 = (_QWORD *)_InterlockedExchange64((volatile __int64 *)this + 3, (__int64)v21);
    if ( v13 )
    {
      v14 = (_QWORD *)((char *)this + 48);
      v15 = *((_QWORD *)this + 6);
      if ( *(GameInputDevice **)(v15 + 8) != (GameInputDevice *)((char *)this + 48) )
        __fastfail(3u);
      *v13 = v15;
      v13[1] = v14;
      *(_QWORD *)(v15 + 8) = v13;
      ++*((_DWORD *)this + 16);
      *v14 = v13;
    }
    else if ( (unsigned int)dword_180069000 > 4
           && (qword_180069010 & 1) != 0
           && (qword_180069018 & 1) == qword_180069018 )
    {
      v16 = *(_QWORD *)v9;
      v19 = *(_WORD *)(*(_QWORD *)v9 + 6LL);
      v20 = *(_WORD *)(v16 + 4);
      v22 = "Device connected";
      v23 = "onecore\\xbox\\gameinput\\client\\GameInputDevice.cpp";
      LODWORD(v21) = 188;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
        v16,
        (unsigned int)&byte_1800598F7,
        v11,
        v12,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v22,
        (__int64)&v20,
        (__int64)&v19);
    }
    *((_DWORD *)this + 20) = 7;
    _mm_mfence();
    v17 = (FeedbackStateCache *)*((_QWORD *)this + 5);
    if ( v17 )
      FeedbackStateCache::WriteToSharedBuffer(v17);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a91c  push    rbp
0x18000a91e  push    rbx
0x18000a91f  push    rsi
0x18000a920  push    rdi
0x18000a921  push    r14
0x18000a923  push    r15
0x18000a925  mov     rbp, rsp
0x18000a928  sub     rsp, 78h
0x18000a92c  mov     rdi, r9
0x18000a92f  mov     rsi, r8
0x18000a932  mov     r14, rdx
0x18000a935  mov     rbx, rcx
0x18000a938  call    ?IsDispatchThread@GameInputDispatcher@@SA_NXZ; GameInputDispatcher::IsDispatchThread(void)
0x18000a93d  test    al, al
0x18000a93f  jz      loc_18000AA7F
0x18000a945  lea     rax, [rbp+var_20]
0x18000a949  mov     [rbp+var_20], 0
0x18000a951  mov     [rsp+78h+var_50], rax; struct SharedBuffer **
0x18000a956  lea     r15, [rbx+20h]
0x18000a95a  mov     r9, rdi; void *
0x18000a95d  mov     [rsp+78h+var_58], r15; struct GameInputDeviceInfo **
0x18000a962  mov     r8, rsi; unsigned __int64
0x18000a965  mov     rdx, r14; struct ISIPCEndpoint *
0x18000a968  mov     rcx, rbx; struct GameInputDevice *
0x18000a96b  call    ?Create@SharedBuffer@@SAJPEAVGameInputDevice@@PEAUISIPCEndpoint@@_KPEAXPEAPEAUGameInputDeviceInfo@@PEAPEAV1@@Z; SharedBuffer::Create(GameInputDevice *,ISIPCEndpoint *,unsigned __int64,void *,GameInputDeviceInfo * *,SharedBuffer * *)
0x18000a970  mov     edi, eax
0x18000a972  test    eax, eax
0x18000a974  js      loc_18000AA63
0x18000a97a  mov     rcx, [rbp+var_20]
0x18000a97e  nop
0x18000a97f  xchg    rcx, [rbx+18h]
0x18000a983  nop
0x18000a984  test    rcx, rcx
0x18000a987  jz      short loc_18000A9B3
0x18000a989  lea     rdx, [rbx+30h]
0x18000a98d  mov     rax, [rdx]
0x18000a990  cmp     [rax+8], rdx
0x18000a994  jz      short loc_18000A99D
0x18000a996  mov     ecx, 3
0x18000a99b  int     29h; Win8: RtlFailFast(ecx)
0x18000a99d  mov     [rcx], rax
0x18000a9a0  mov     [rcx+8], rdx
0x18000a9a4  mov     [rax+8], rcx
0x18000a9a8  inc     dword ptr [rdx+10h]
0x18000a9ab  mov     [rdx], rcx
0x18000a9ae  jmp     loc_18000AA48
0x18000a9b3  mov     eax, cs:dword_180069000
0x18000a9b9  cmp     eax, 4
0x18000a9bc  jbe     loc_18000AA48
0x18000a9c2  mov     rcx, cs:qword_180069018
0x18000a9c9  mov     rax, cs:qword_180069010
0x18000a9d0  test    al, 1
0x18000a9d2  jz      short loc_18000AA48
0x18000a9d4  mov     rax, rcx
0x18000a9d7  and     eax, 1
0x18000a9da  cmp     rax, rcx
0x18000a9dd  jnz     short loc_18000AA48
0x18000a9df  mov     rcx, [r15]
0x18000a9e2  lea     rdx, byte_1800598F7
0x18000a9e9  movzx   eax, word ptr [rcx+6]
0x18000a9ed  mov     [rbp+var_28], ax
0x18000a9f1  movzx   eax, word ptr [rcx+4]
0x18000a9f5  mov     [rbp+var_26], ax
0x18000a9f9  lea     rax, aDeviceConnecte; "Device connected"
0x18000aa00  mov     [rbp+var_18], rax
0x18000aa04  lea     rax, aOnecoreXboxGam_49; "onecore\\xbox\\gameinput\\client\\GameI"...
0x18000aa0b  mov     [rbp+var_10], rax
0x18000aa0f  lea     rax, [rbp+var_28]
0x18000aa13  mov     [rsp+78h+var_38], rax
0x18000aa18  lea     rax, [rbp+var_26]
0x18000aa1c  mov     [rsp+78h+var_40], rax
0x18000aa21  lea     rax, [rbp+var_18]
0x18000aa25  mov     [rsp+78h+var_48], rax
0x18000aa2a  lea     rax, [rbp+var_20]
0x18000aa2e  mov     [rsp+78h+var_50], rax
0x18000aa33  lea     rax, [rbp+var_10]
0x18000aa37  mov     [rsp+78h+var_58], rax
0x18000aa3c  mov     dword ptr [rbp+var_20], 0BCh
0x18000aa43  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$01@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$01@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &)
0x18000aa48  nop
0x18000aa49  mov     dword ptr [rbx+50h], 7
0x18000aa50  mfence
0x18000aa53  mov     rcx, [rbx+28h]; this
0x18000aa57  test    rcx, rcx
0x18000aa5a  jz      short loc_18000AA6F
0x18000aa5c  call    ?WriteToSharedBuffer@FeedbackStateCache@@QEBAXXZ; FeedbackStateCache::WriteToSharedBuffer(void)
0x18000aa61  jmp     short loc_18000AA6F
0x18000aa63  mov     rdx, [rbp+arg_20]; void *
0x18000aa67  mov     rcx, rbx; this
0x18000aa6a  call    ?RemoveBuffer@GameInputDevice@@QEAAXPEBX@Z; GameInputDevice::RemoveBuffer(void const *)
0x18000aa6f  mov     eax, edi
0x18000aa71  add     rsp, 78h
0x18000aa75  pop     r15
0x18000aa77  pop     r14
0x18000aa79  pop     rdi
0x18000aa7a  pop     rsi
0x18000aa7b  pop     rbx
0x18000aa7c  pop     rbp
0x18000aa7d  retn
0x18000aa7f  mov     edx, 0A0h
0x18000aa84  mov     ecx, 8000FFFFh
0x18000aa89  call    GameInputFailFast
```
