# OnDemandBrokerClient::GetLaunchInfo(_GUID const *,_OdbLaunchInfo * *)

- ea: `0x180003af0`
- end: `0x180003bb1`
- name: `?GetLaunchInfo@OnDemandBrokerClient@@UEAAJPEBU_GUID@@PEAPEAU_OdbLaunchInfo@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *__hidden this, const struct _GUID *, struct _OdbLaunchInfo **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003af0`
- `0x180004d50`
- `0x180007010`

## import_xrefs

- `msvcrt!free` at `0x180003b7b`
- `msvcrt!free` at `0x180003b7b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003b85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003b85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003b17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003b17`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::GetLaunchInfo(
        OnDemandBrokerClient *this,
        const struct _GUID *a2,
        struct _OdbLaunchInfo **a3)
{
  int v6; // esi
  struct _OdbLaunchInfo *v7; // rax
  _QWORD *v8; // rcx
  void *v9; // rcx
  void *Block; // [rsp+40h] [rbp+8h] BYREF

  Block = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( a2 && a3 )
  {
    *a3 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, void **))(**((_QWORD **)this + 8) + 88LL))(
           *((_QWORD *)this + 8),
           a2,
           &Block);
    if ( v6 >= 0 )
    {
      v7 = (struct _OdbLaunchInfo *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v7 )
      {
        v8 = Block;
        *(_OWORD *)v7 = *(_OWORD *)Block;
        *((_QWORD *)v7 + 2) = v8[2];
        v9 = Block;
        *a3 = v7;
        free(v9);
      }
      else
      {
        *a3 = 0;
        v6 = -2147024882;
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003af0  mov     [rsp+arg_8], rbx
0x180003af5  mov     [rsp+arg_10], rbp
0x180003afa  push    rsi
0x180003afb  push    rdi
0x180003afc  push    r14
0x180003afe  sub     rsp, 20h
0x180003b02  mov     rbp, rcx
0x180003b05  xor     r14d, r14d
0x180003b08  add     rcx, 8; lpCriticalSection
0x180003b0c  mov     [rsp+38h+Block], r14
0x180003b11  mov     rbx, r8
0x180003b14  mov     rsi, rdx
0x180003b17  call    cs:__imp_EnterCriticalSection
0x180003b1d  test    rsi, rsi
0x180003b20  jz      short loc_180003BA0
0x180003b22  test    rbx, rbx
0x180003b25  jz      short loc_180003BA0
0x180003b27  mov     [rbx], r14
0x180003b2a  lea     r8, [rsp+38h+Block]
0x180003b2f  mov     rcx, [rbp+40h]
0x180003b33  mov     rdx, rsi
0x180003b36  mov     rax, [rcx]
0x180003b39  mov     rax, [rax+58h]
0x180003b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b42  mov     esi, eax
0x180003b44  test    eax, eax
0x180003b46  js      short loc_180003B81
0x180003b48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003b4f  mov     ecx, 18h; unsigned __int64
0x180003b54  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180003b59  test    rax, rax
0x180003b5c  jz      short loc_180003BA7
0x180003b5e  mov     rcx, [rsp+38h+Block]
0x180003b63  movups  xmm0, xmmword ptr [rcx]
0x180003b66  movups  xmmword ptr [rax], xmm0
0x180003b69  movsd   xmm1, qword ptr [rcx+10h]
0x180003b6e  movsd   qword ptr [rax+10h], xmm1
0x180003b73  mov     rcx, [rsp+38h+Block]; Block
0x180003b78  mov     [rbx], rax
0x180003b7b  call    cs:__imp_free
0x180003b81  lea     rcx, [rbp+8]; lpCriticalSection
0x180003b85  call    cs:__imp_LeaveCriticalSection
0x180003b8b  mov     rbx, [rsp+38h+arg_8]
0x180003b90  mov     eax, esi
0x180003b92  mov     rbp, [rsp+38h+arg_10]
0x180003b97  add     rsp, 20h
0x180003b9b  pop     r14
0x180003b9d  pop     rdi
0x180003b9e  pop     rsi
0x180003b9f  retn
0x180003ba0  mov     esi, 80070057h
0x180003ba5  jmp     short loc_180003B81
0x180003ba7  mov     [rbx], r14
0x180003baa  mov     esi, 8007000Eh
0x180003baf  jmp     short loc_180003B81
```
