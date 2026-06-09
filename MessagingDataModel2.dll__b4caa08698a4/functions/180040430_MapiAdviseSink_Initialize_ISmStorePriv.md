# MapiAdviseSink::Initialize(ISmStorePriv *)

- ea: `0x180040430`
- end: `0x18004055c`
- name: `?Initialize@MapiAdviseSink@@QEAAJPEAUISmStorePriv@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(MapiAdviseSink *__hidden this, struct ISmStorePriv *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000be18`
- `0x180012f08`
- `0x18002416c`
- `0x180040430`
- `0x18004058c`
- `0x1800405bc`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040507`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180040507`
- `CEMAPI!MAPIFreeBuffer` at `0x1800404d0`
- `CEMAPI!MAPIFreeBuffer` at `0x180040537`
- `CEMAPI!MAPIFreeBuffer` at `0x1800404d0`
- `CEMAPI!MAPIFreeBuffer` at `0x180040537`
- `CEMAPI!HrGetOneProp` at `0x1800404aa`
- `CEMAPI!HrGetOneProp` at `0x1800404aa`

## pseudocode

```c
__int64 __fastcall MapiAdviseSink::Initialize(MapiAdviseSink *this, struct ISmStorePriv *a2)
{
  CEntryId *v2; // rdi
  void **v4; // rbx
  struct IMAPIProp *v5; // rax
  HRESULT OneProp; // ebx
  HANDLE EventW; // rax
  LPVOID pv; // [rsp+30h] [rbp-18h] BYREF

  v2 = (MapiAdviseSink *)((char *)this + 144);
  *((_QWORD *)this + 8) = a2;
  if ( *((_DWORD *)this + 36) )
  {
    Log_AssertionEvent_15(this, a2, 68);
    if ( *(_DWORD *)v2 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  pv = 0;
  v4 = tlx::replace<_SPropValue *,unsigned long (*)(void *),&unsigned long MAPIFreeBuffer(void *),0>(&pv);
  v5 = (struct IMAPIProp *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 512LL))(*((_QWORD *)this + 8));
  OneProp = HrGetOneProp(v5, 0x35E20102u, (LPSPropValue *)v4);
  if ( OneProp < 0 )
    goto LABEL_5;
  OneProp = CEntryId::Set(v2, *((_DWORD *)pv + 2), *((struct ENTRYID **)pv + 2));
  if ( OneProp < 0 )
    goto LABEL_5;
  EventW = CreateEventW(0, 1, 1, 0);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::reset((char *)this + 72, EventW);
  if ( !*((_QWORD *)this + 9) )
  {
    OneProp = -2147024882;
LABEL_5:
    Log_HREvent_16(OneProp);
    if ( pv )
      MAPIFreeBuffer(pv);
    return (unsigned int)OneProp;
  }
  if ( pv )
    MAPIFreeBuffer(pv);
  return 0;
}

```

## disassembly

```asm
0x180040430  mov     [rsp+arg_8], rbx
0x180040435  mov     [rsp+arg_10], rsi
0x18004043a  push    rdi
0x18004043b  sub     rsp, 40h
0x18004043f  mov     rax, cs:__security_cookie
0x180040446  xor     rax, rsp
0x180040449  mov     [rsp+48h+var_10], rax
0x18004044e  lea     rdi, [rcx+90h]
0x180040455  mov     [rcx+40h], rdx
0x180040459  cmp     dword ptr [rdi], 0
0x18004045c  mov     rsi, rcx
0x18004045f  jz      short loc_180040476
0x180040461  mov     r8d, 44h ; 'D'
0x180040467  call    Log_AssertionEvent_15
0x18004046c  cmp     dword ptr [rdi], 0
0x18004046f  jz      short loc_180040476
0x180040471  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180040476  lea     rcx, [rsp+48h+pv]
0x18004047b  mov     [rsp+48h+pv], 0
0x180040484  call    ??$replace@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@tlx@@YAPEAPEAU_SPropValue@@AEAV?$auto_xxx@PEAU_SPropValue@@P6AKPEAX@Z$1?MAPIFreeBuffer@@YAK0@Z$0A@@0@@Z; tlx::replace<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0>(tlx::auto_xxx<_SPropValue *,ulong (*)(void *),&MAPIFreeBuffer(void *),0> &)
0x180040489  mov     rcx, [rsi+40h]
0x18004048d  mov     rbx, rax
0x180040490  mov     rdx, [rcx]
0x180040493  mov     rax, [rdx+200h]
0x18004049a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004049f  mov     r8, rbx; lppProp
0x1800404a2  mov     edx, 35E20102h; ulPropTag
0x1800404a7  mov     rcx, rax; lpMapiProp
0x1800404aa  call    cs:__imp_HrGetOneProp
0x1800404b0  mov     ebx, eax
0x1800404b2  test    eax, eax
0x1800404b4  jns     short loc_1800404DA
0x1800404b6  mov     edx, 1
0x1800404bb  lea     r9d, [rdx+46h]
0x1800404bf  mov     ecx, ebx; int
0x1800404c1  call    Log_HREvent_16
0x1800404c6  mov     rcx, [rsp+48h+pv]; pv
0x1800404cb  test    rcx, rcx
0x1800404ce  jz      short loc_1800404D6
0x1800404d0  call    cs:__imp_MAPIFreeBuffer
0x1800404d6  mov     eax, ebx
0x1800404d8  jmp     short loc_18004053F
0x1800404da  mov     rdx, [rsp+48h+pv]
0x1800404df  mov     rcx, rdi; this
0x1800404e2  mov     r8, [rdx+10h]; struct ENTRYID *
0x1800404e6  mov     edx, [rdx+8]; unsigned int
0x1800404e9  call    ?Set@CEntryId@@QEAAJKPEAUENTRYID@@@Z; CEntryId::Set(ulong,ENTRYID *)
0x1800404ee  mov     ebx, eax
0x1800404f0  mov     edx, 1; bManualReset
0x1800404f5  test    eax, eax
0x1800404f7  jns     short loc_1800404FF
0x1800404f9  lea     r9d, [rdx+47h]
0x1800404fd  jmp     short loc_1800404BF
0x1800404ff  xor     r9d, r9d; lpName
0x180040502  xor     ecx, ecx; lpEventAttributes
0x180040504  mov     r8d, edx; bInitialState
0x180040507  call    cs:__imp_CreateEventW
0x18004050d  mov     rdx, rax
0x180040510  lea     rcx, [rsi+48h]
0x180040514  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::reset(void *)
0x180040519  cmp     qword ptr [rsi+48h], 0
0x18004051e  jnz     short loc_18004052D
0x180040520  xor     edx, edx
0x180040522  mov     ebx, 8007000Eh
0x180040527  lea     r9d, [rdx+4Bh]
0x18004052b  jmp     short loc_1800404BF
0x18004052d  mov     rcx, [rsp+48h+pv]; pv
0x180040532  test    rcx, rcx
0x180040535  jz      short loc_18004053D
0x180040537  call    cs:__imp_MAPIFreeBuffer
0x18004053d  xor     eax, eax
0x18004053f  mov     rcx, [rsp+48h+var_10]
0x180040544  xor     rcx, rsp; StackCookie
0x180040547  call    __security_check_cookie
0x18004054c  mov     rbx, [rsp+48h+arg_8]
0x180040551  mov     rsi, [rsp+48h+arg_10]
0x180040556  add     rsp, 40h
0x18004055a  pop     rdi
0x18004055b  retn
```
