# CWwanSmsDevice::OnSetSmsConfigComplete(WWAN_INTERFACE_OBJECT *)

- ea: `0x18004bea8`
- end: `0x18004bfd0`
- name: `?OnSetSmsConfigComplete@CWwanSmsDevice@@AEAAXPEAUWWAN_INTERFACE_OBJECT@@@Z`
- size: `296`
- prototype: `void __fastcall(CWwanSmsDevice *__hidden this, struct WWAN_INTERFACE_OBJECT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004cb00`

## callees

- `0x18004bea8`
- `0x180051628`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004bfb0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004bfb0`

## string_xrefs

- `0x18004bfa0`: `CWwanSmsDevice::OnSetSmsConfigComplete`
- `0x18004bf94`: `Set sms configuration completed for apiId: %d, result: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWwanSmsDevice::OnSetSmsConfigComplete(CWwanSmsDevice *this, struct WWAN_INTERFACE_OBJECT *a2)
{
  char *v4; // rdi
  unsigned int v5; // r8d
  signed int v6; // ecx
  signed int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rax

  v4 = (char *)this + 32;
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  if ( *((_QWORD *)this + 26) )
  {
    v5 = *((_DWORD *)a2 + 525);
    v6 = 16807 * ((v5 ^ 0xDEADBEEF) & 0x7FFFFFFF) - 0x7FFFFFFF * (((v5 ^ 0xDEADBEEF) & 0x7FFFFFFF) / 0x1F31D);
    v7 = v6 + 0x7FFFFFFF;
    if ( v6 >= 0 )
      v7 = 16807 * ((*((_DWORD *)a2 + 525) ^ 0xDEADBEEF) & 0x7FFFFFFF)
         - 0x7FFFFFFF * (((*((_DWORD *)a2 + 525) ^ 0xDEADBEEF) & 0x7FFFFFFF) / 0x1F31D);
    v8 = 2 * (*((_QWORD *)this + 30) & v7);
    v9 = *((_QWORD *)this + 27);
    v10 = *(_QWORD *)(v9 + 8 * v8 + 8);
    v11 = *((_QWORD *)this + 25);
    if ( v10 == v11 )
    {
LABEL_5:
      v10 = 0;
    }
    else
    {
      v12 = *(_QWORD *)(v9 + 8 * v8);
      while ( v5 < *(_DWORD *)(v10 + 16) )
      {
        if ( v10 == v12 )
          goto LABEL_5;
        v10 = *(_QWORD *)(v10 + 8);
      }
      if ( *(_DWORD *)(v10 + 16) < v5 )
        v10 = 0;
    }
    if ( !v10 )
      v10 = *((_QWORD *)this + 25);
    if ( v10 != v11 )
    {
      *(_DWORD *)(v10 + 32) = *((_DWORD *)a2 + 529);
      LogSmsRouterInfo(
        "CWwanSmsDevice::OnSetSmsConfigComplete",
        0x412u,
        "Set sms configuration completed for apiId: %d, result: %d",
        *((_DWORD *)a2 + 525),
        *((_DWORD *)a2 + 529));
      SetEvent(*(HANDLE *)(v10 + 24));
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))(v4);
}

```

## disassembly

```asm
0x18004bea8  push    rbx
0x18004beaa  push    rbp
0x18004beab  push    rsi
0x18004beac  push    rdi
0x18004bead  sub     rsp, 48h
0x18004beb1  mov     rsi, rdx
0x18004beb4  mov     rbp, rcx
0x18004beb7  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18004bebe  mov     [rsp+68h+var_38], rax
0x18004bec3  lea     rdi, [rcx+20h]
0x18004bec7  mov     [rsp+68h+var_30], rdi
0x18004becc  mov     rax, [rdi]
0x18004becf  mov     rcx, rdi
0x18004bed2  mov     rax, [rax]
0x18004bed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004beda  nop
0x18004bedb  cmp     qword ptr [rbp+0D0h], 0
0x18004bee3  jbe     loc_18004BFB7
0x18004bee9  mov     r8d, [rsi+834h]
0x18004bef0  mov     ecx, r8d
0x18004bef3  xor     ecx, 0DEADBEEFh
0x18004bef9  btr     ecx, 1Fh
0x18004befd  mov     eax, 69C16BDh
0x18004bf02  mul     ecx
0x18004bf04  mov     eax, ecx
0x18004bf06  sub     eax, edx
0x18004bf08  shr     eax, 1
0x18004bf0a  add     eax, edx
0x18004bf0c  shr     eax, 10h
0x18004bf0f  imul    eax, 7FFFFFFFh
0x18004bf15  imul    ecx, 41A7h
0x18004bf1b  sub     ecx, eax
0x18004bf1d  lea     eax, [rcx+7FFFFFFFh]
0x18004bf23  cmovns  eax, ecx
0x18004bf26  movsxd  rcx, eax
0x18004bf29  and     rcx, [rbp+0F0h]
0x18004bf30  add     rcx, rcx
0x18004bf33  mov     rax, [rbp+0D8h]
0x18004bf3a  mov     rbx, [rax+rcx*8+8]
0x18004bf3f  mov     rdx, [rbp+0C8h]
0x18004bf46  cmp     rbx, rdx
0x18004bf49  jnz     short loc_18004BF4F
0x18004bf4b  xor     ebx, ebx
0x18004bf4d  jmp     short loc_18004BF6E
0x18004bf4f  mov     rax, [rax+rcx*8]
0x18004bf53  cmp     r8d, [rbx+10h]
0x18004bf57  jnb     short loc_18004BF64
0x18004bf59  cmp     rbx, rax
0x18004bf5c  jz      short loc_18004BF4B
0x18004bf5e  mov     rbx, [rbx+8]
0x18004bf62  jmp     short loc_18004BF53
0x18004bf64  xor     eax, eax
0x18004bf66  cmp     [rbx+10h], r8d
0x18004bf6a  cmovb   rbx, rax
0x18004bf6e  test    rbx, rbx
0x18004bf71  cmovz   rbx, rdx
0x18004bf75  cmp     rbx, rdx
0x18004bf78  jz      short loc_18004BFB7
0x18004bf7a  mov     eax, [rsi+844h]
0x18004bf80  mov     [rbx+20h], eax
0x18004bf83  mov     eax, [rsi+844h]
0x18004bf89  mov     [rsp+68h+var_48], eax
0x18004bf8d  mov     r9d, [rsi+834h]
0x18004bf94  lea     r8, aSetSmsConfigur; "Set sms configuration completed for api"...
0x18004bf9b  mov     edx, 412h; unsigned int
0x18004bfa0  lea     rcx, aCwwansmsdevice_9; "CWwanSmsDevice::OnSetSmsConfigComplete"
0x18004bfa7  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18004bfac  mov     rcx, [rbx+18h]; hEvent
0x18004bfb0  call    cs:__imp_SetEvent
0x18004bfb6  nop
0x18004bfb7  mov     rax, [rdi]
0x18004bfba  mov     rcx, rdi
0x18004bfbd  mov     rax, [rax+8]
0x18004bfc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfc6  nop
0x18004bfc7  add     rsp, 48h
0x18004bfcb  pop     rdi
0x18004bfcc  pop     rsi
0x18004bfcd  pop     rbp
0x18004bfce  pop     rbx
0x18004bfcf  retn
```
