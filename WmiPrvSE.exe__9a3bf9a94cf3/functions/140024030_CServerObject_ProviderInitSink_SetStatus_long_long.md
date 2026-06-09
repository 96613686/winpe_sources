# CServerObject_ProviderInitSink::SetStatus(long,long)

- ea: `0x140024030`
- end: `0x1400240e4`
- name: `?SetStatus@CServerObject_ProviderInitSink@@UEAAJJJ@Z`
- size: `180`
- prototype: `__int64 __fastcall(CServerObject_ProviderInitSink *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400234b8`
- `0x140024030`
- `0x1400415d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002405a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002405a`
- `wbemcomn!GetMemLogObject` at `0x1400240b1`
- `wbemcomn!GetMemLogObject` at `0x1400240b1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400240bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400240bc`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14002408f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14002408f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400240a9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1400240a9`

## pseudocode

```c
__int64 __fastcall CServerObject_ProviderInitSink::SetStatus(CServerObject_ProviderInitSink *this, int a2)
{
  int v2; // ebx
  int v5; // eax
  WINBOOL v7; // edx
  struct _GENERIC_MAPPING *v8; // r8
  CMemoryLog *MemLogObject; // rax

  v2 = 0;
  if ( *((_QWORD *)this + 4) )
  {
    v2 = CoImpersonateClient();
    if ( v2 >= 0 )
    {
      v2 = ProviderSubSystem_Common_Globals::Check_SecurityDescriptor_CallIdentity(
             *((struct _SECURITY_DESCRIPTOR **)this + 4),
             v7,
             v8,
             0);
      CoRevertToSelf();
    }
  }
  v5 = v2;
  if ( v2 >= 0 )
    v5 = a2;
  *((_DWORD *)this + 6) = v5;
  SetEvent(*((HANDLE *)this + 2));
  if ( v2 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v2);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ac9f0bf1ae8b30a0c82e8edf46eb550d_Traceguids, (unsigned int)v2);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140024030  mov     [rsp+arg_0], rbx
0x140024035  mov     [rsp+arg_8], rsi
0x14002403a  push    rdi
0x14002403b  sub     rsp, 20h
0x14002403f  xor     ebx, ebx
0x140024041  mov     esi, edx
0x140024043  mov     rdi, rcx
0x140024046  cmp     [rcx+20h], rbx
0x14002404a  jnz     short loc_14002408F
0x14002404c  mov     eax, ebx
0x14002404e  test    ebx, ebx
0x140024050  cmovns  eax, esi
0x140024053  mov     [rdi+18h], eax
0x140024056  mov     rcx, [rdi+10h]; hEvent
0x14002405a  call    cs:__imp_SetEvent
0x140024060  test    ebx, ebx
0x140024062  js      short loc_1400240B1
0x140024064  mov     rcx, cs:WPP_GLOBAL_Control
0x14002406b  lea     rax, WPP_GLOBAL_Control
0x140024072  cmp     rcx, rax
0x140024075  jz      short loc_14002407D
0x140024077  test    byte ptr [rcx+1Ch], 4
0x14002407b  jnz     short loc_1400240C4
0x14002407d  mov     rsi, [rsp+28h+arg_8]
0x140024082  mov     eax, ebx
0x140024084  mov     rbx, [rsp+28h+arg_0]
0x140024089  add     rsp, 20h
0x14002408d  pop     rdi
0x14002408e  retn
0x14002408f  call    cs:__imp_CoImpersonateClient
0x140024095  mov     ebx, eax
0x140024097  test    eax, eax
0x140024099  js      short loc_14002404C
0x14002409b  mov     rcx, [rdi+20h]; struct _SECURITY_DESCRIPTOR *
0x14002409f  xor     r9d, r9d; struct _SECURITY_DESCRIPTOR *
0x1400240a2  call    ?Check_SecurityDescriptor_CallIdentity@ProviderSubSystem_Common_Globals@@SAJPEAU_SECURITY_DESCRIPTOR@@KPEAU_GENERIC_MAPPING@@0@Z; ProviderSubSystem_Common_Globals::Check_SecurityDescriptor_CallIdentity(_SECURITY_DESCRIPTOR *,ulong,_GENERIC_MAPPING *,_SECURITY_DESCRIPTOR *)
0x1400240a7  mov     ebx, eax
0x1400240a9  call    cs:__imp_CoRevertToSelf
0x1400240af  jmp     short loc_14002404C
0x1400240b1  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1400240b7  mov     rcx, rax
0x1400240ba  mov     edx, ebx
0x1400240bc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1400240c2  jmp     short loc_140024064
0x1400240c4  cmp     byte ptr [rcx+19h], 2
0x1400240c8  jb      short loc_14002407D
0x1400240ca  mov     rcx, [rcx+10h]
0x1400240ce  lea     r8, WPP_ac9f0bf1ae8b30a0c82e8edf46eb550d_Traceguids
0x1400240d5  mov     edx, 0Bh
0x1400240da  mov     r9d, ebx
0x1400240dd  call    WPP_SF_d
0x1400240e2  jmp     short loc_14002407D
```
