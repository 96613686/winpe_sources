# FeedbackManager::OnClientSignal(void)

- ea: `0x1800182dc`
- end: `0x180018389`
- name: `?OnClientSignal@FeedbackManager@@QEAAXXZ`
- size: `173`
- prototype: `void __fastcall(FeedbackManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180042b60`

## callees

- `0x180001304`
- `0x1800182dc`

## import_xrefs

- `ntdll!NtAlertThread` at `0x180018304`
- `ntdll!NtAlertThread` at `0x180018304`

## pseudocode

```c
void __fastcall FeedbackManager::OnClientSignal(HANDLE *this)
{
  NTSTATUS v1; // r8d
  int v2; // r9d
  NTSTATUS v3; // [rsp+50h] [rbp+8h] BYREF
  int v4; // [rsp+58h] [rbp+10h] BYREF
  const char *v5; // [rsp+60h] [rbp+18h] BYREF

  *((_BYTE *)*this + 168) = 1;
  _mm_mfence();
  if ( !*((_BYTE *)*this + 169) )
  {
    v1 = NtAlertThread(this[1]);
    if ( v1 < 0
      && (unsigned int)dword_180069000 > 2
      && (qword_180069010 & 8) != 0
      && (qword_180069018 & 8) == qword_180069018 )
    {
      v3 = v1;
      v5 = "onecore\\xbox\\gameinput\\feedback\\FeedbackManager.cpp";
      v4 = 250;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069010,
        (unsigned int)byte_18005E56D,
        v1,
        v2,
        (__int64)&v5,
        (__int64)&v4,
        (__int64)&v3);
    }
  }
}

```

## disassembly

```asm
0x1800182dc  sub     rsp, 48h
0x1800182e0  mov     rax, [rcx]
0x1800182e3  nop
0x1800182e4  mov     byte ptr [rax+0A8h], 1
0x1800182eb  mfence
0x1800182ee  mov     rax, [rcx]
0x1800182f1  mov     dl, [rax+0A9h]
0x1800182f7  nop
0x1800182f8  test    dl, dl
0x1800182fa  jnz     loc_180018383
0x180018300  mov     rcx, [rcx+8]; ThreadHandle
0x180018304  call    cs:__imp_NtAlertThread
0x18001830b  nop     dword ptr [rax+rax+00h]
0x180018310  mov     r8d, eax
0x180018313  test    eax, eax
0x180018315  jns     short loc_180018383
0x180018317  mov     ecx, cs:dword_180069000
0x18001831d  cmp     ecx, 2
0x180018320  jbe     short loc_180018383
0x180018322  mov     rdx, cs:qword_180069018
0x180018329  mov     rcx, cs:qword_180069010
0x180018330  test    cl, 8
0x180018333  jz      short loc_180018383
0x180018335  mov     rax, rdx
0x180018338  and     eax, 8
0x18001833b  cmp     rax, rdx
0x18001833e  jnz     short loc_180018383
0x180018340  lea     rax, aOnecoreXboxGam_10; "onecore\\xbox\\gameinput\\feedback\\Fee"...
0x180018347  mov     [rsp+48h+arg_0], r8d
0x18001834c  mov     [rsp+48h+arg_10], rax
0x180018351  lea     rdx, byte_18005E56D
0x180018358  lea     rax, [rsp+48h+arg_0]
0x18001835d  mov     [rsp+48h+arg_8], 0FAh
0x180018365  mov     [rsp+48h+var_18], rax
0x18001836a  lea     rax, [rsp+48h+arg_8]
0x18001836f  mov     [rsp+48h+var_20], rax
0x180018374  lea     rax, [rsp+48h+arg_10]
0x180018379  mov     [rsp+48h+var_28], rax
0x18001837e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018383  add     rsp, 48h
0x180018387  retn
```
