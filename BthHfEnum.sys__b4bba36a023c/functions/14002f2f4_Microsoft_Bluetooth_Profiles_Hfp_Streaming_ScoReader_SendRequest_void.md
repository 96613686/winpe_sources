# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::SendRequest(void)

- ea: `0x14002f2f4`
- end: `0x14002f425`
- name: `?SendRequest@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAA_NXZ`
- size: `305`
- prototype: `bool __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002f250`

## callees

- `0x140016a3c`
- `0x140017b44`
- `0x140017ba4`
- `0x140017c0c`
- `0x140017cb8`
- `0x14001ae00`
- `0x14002f080`
- `0x14002f2f4`

## pseudocode

```c
char __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::SendRequest(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *this)
{
  unsigned __int64 v1; // rdx
  struct WDFREQUEST__ *v3; // rdi
  struct WDFQUEUE__ *v4; // rcx
  char v5; // si
  int v6; // ecx
  int v7; // eax
  int v8; // ebp
  struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *ContextFromObject; // rax
  __int64 v10; // r9
  struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *v12; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 2);
  v3 = 0;
  v4 = *(struct WDFQUEUE__ **)this;
  v5 = 0;
  v12 = 0;
  v6 = Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext::MakeAndAttachToNewBrb(v4, v1, &v12);
  if ( v6 >= 0 )
    v3 = *(struct WDFREQUEST__ **)v12;
  v7 = 0;
  if ( v6 < 0 )
    v7 = v6;
  if ( v7 >= 0 )
  {
    Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::IncrementPendingRequestCounter(this);
    v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void (*)(struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, void *), Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *, struct WDFREQUEST__ *))(**((_QWORD **)this + 1) + 8LL))(
           *((_QWORD *)this + 1),
           *(_QWORD *)this,
           Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::RequestCompletionRoutine,
           this,
           v3);
    if ( v8 >= 0 )
    {
      ContextFromObject = Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext::GetContextFromObject(v3);
      v10 = (unsigned int)_InterlockedExchange(
                            (volatile __int32 *)ContextFromObject + 16,
                            *((_DWORD *)ContextFromObject + 16));
      if ( (_DWORD)v10 == 259 )
        return 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_b61ba7c6c7ba3c52b18b4774502f69e2_Traceguids, v10, this);
      }
      return v5;
    }
    Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::DecrementPendingRequestCounter(this);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        WPP_b61ba7c6c7ba3c52b18b4774502f69e2_Traceguids,
        (unsigned int)v8,
        this);
    }
  }
  if ( v3 )
    Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::ReturnRequestToPool(v3);
  return v5;
}

```

## disassembly

```asm
0x14002f2f4  push    rbx
0x14002f2f6  push    rbp
0x14002f2f7  push    rsi
0x14002f2f8  push    rdi
0x14002f2f9  sub     rsp, 38h
0x14002f2fd  mov     rdx, [rcx+10h]; unsigned __int64
0x14002f301  lea     r8, [rsp+58h+arg_0]; struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext **
0x14002f306  mov     rbx, rcx
0x14002f309  xor     edi, edi
0x14002f30b  mov     rcx, [rcx]; struct WDFQUEUE__ *
0x14002f30e  xor     sil, sil
0x14002f311  mov     [rsp+58h+arg_0], rdi
0x14002f316  call    ?MakeAndAttachToNewBrb@RequestContext@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@SAJPEAUWDFQUEUE__@@_KPEAPEAV123456@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext::MakeAndAttachToNewBrb(WDFQUEUE__ *,unsigned __int64,Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext * *)
0x14002f31b  mov     ecx, eax
0x14002f31d  test    eax, eax
0x14002f31f  js      short loc_14002F329
0x14002f321  mov     rax, [rsp+58h+arg_0]
0x14002f326  mov     rdi, [rax]
0x14002f329  xor     eax, eax
0x14002f32b  test    ecx, ecx
0x14002f32d  cmovs   eax, ecx
0x14002f330  test    eax, eax
0x14002f332  js      loc_14002F40B
0x14002f338  mov     rcx, rbx; this
0x14002f33b  call    ?IncrementPendingRequestCounter@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAXXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::IncrementPendingRequestCounter(void)
0x14002f340  mov     rcx, [rbx+8]
0x14002f344  lea     r8, ?RequestCompletionRoutine@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@CAXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::RequestCompletionRoutine(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)
0x14002f34b  mov     rdx, [rbx]
0x14002f34e  mov     r9, rbx
0x14002f351  mov     [rsp+58h+var_38], rdi
0x14002f356  mov     rax, [rcx]
0x14002f359  mov     rax, [rax+8]
0x14002f35d  call    _guard_dispatch_icall
0x14002f362  mov     ebp, eax
0x14002f364  test    eax, eax
0x14002f366  js      short loc_14002F3C6
0x14002f368  mov     rcx, rdi; struct WDFREQUEST__ *
0x14002f36b  call    ?GetContextFromObject@RequestContext@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@SAPEAV123456@PEAUWDFREQUEST__@@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext::GetContextFromObject(WDFREQUEST__ *)
0x14002f370  mov     r9d, [rax+40h]
0x14002f374  xchg    r9d, [rax+40h]
0x14002f378  cmp     r9d, 103h
0x14002f37f  jz      short loc_14002F3C1
0x14002f381  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f388  lea     rax, WPP_GLOBAL_Control
0x14002f38f  cmp     rcx, rax
0x14002f392  jz      loc_14002F418
0x14002f398  mov     eax, [rcx+2Ch]
0x14002f39b  test    al, 10h
0x14002f39d  jz      short loc_14002F418
0x14002f39f  cmp     byte ptr [rcx+29h], 4
0x14002f3a3  jb      short loc_14002F418
0x14002f3a5  mov     rcx, [rcx+18h]
0x14002f3a9  lea     r8, WPP_b61ba7c6c7ba3c52b18b4774502f69e2_Traceguids
0x14002f3b0  mov     edx, 0Ch
0x14002f3b5  mov     [rsp+58h+var_38], rbx
0x14002f3ba  call    WPP_SF_dq
0x14002f3bf  jmp     short loc_14002F418
0x14002f3c1  mov     sil, 1
0x14002f3c4  jmp     short loc_14002F418
0x14002f3c6  mov     rcx, rbx; this
0x14002f3c9  call    ?DecrementPendingRequestCounter@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAXXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::DecrementPendingRequestCounter(void)
0x14002f3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f3d5  lea     rax, WPP_GLOBAL_Control
0x14002f3dc  cmp     rcx, rax
0x14002f3df  jz      short loc_14002F40B
0x14002f3e1  mov     eax, [rcx+2Ch]
0x14002f3e4  test    al, 10h
0x14002f3e6  jz      short loc_14002F40B
0x14002f3e8  cmp     byte ptr [rcx+29h], 3
0x14002f3ec  jb      short loc_14002F40B
0x14002f3ee  mov     rcx, [rcx+18h]
0x14002f3f2  lea     r8, WPP_b61ba7c6c7ba3c52b18b4774502f69e2_Traceguids
0x14002f3f9  mov     edx, 0Dh
0x14002f3fe  mov     [rsp+58h+var_38], rbx
0x14002f403  mov     r9d, ebp
0x14002f406  call    WPP_SF_dq
0x14002f40b  test    rdi, rdi
0x14002f40e  jz      short loc_14002F418
0x14002f410  mov     rcx, rdi; struct WDFREQUEST__ *
0x14002f413  call    ?ReturnRequestToPool@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@SAXPEAUWDFREQUEST__@@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::ReturnRequestToPool(WDFREQUEST__ *)
0x14002f418  mov     al, sil
0x14002f41b  add     rsp, 38h
0x14002f41f  pop     rdi
0x14002f420  pop     rsi
0x14002f421  pop     rbp
0x14002f422  pop     rbx
0x14002f423  retn
```
