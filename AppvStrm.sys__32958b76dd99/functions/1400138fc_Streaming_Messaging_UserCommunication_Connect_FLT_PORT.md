# Streaming::Messaging::UserCommunication::Connect(_FLT_PORT *)

- ea: `0x1400138fc`
- end: `0x140013a0f`
- name: `?Connect@UserCommunication@Messaging@Streaming@@QEAAJPEAU_FLT_PORT@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(PERESOURCE *this, struct _ERESOURCE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140013e80`

## callees

- `0x1400138fc`
- `0x1400147fc`
- `0x1400153c4`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013964`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013998`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013964`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013998`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013958`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001398c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013958`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001398c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001392d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001392d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013915`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013915`

## string_xrefs

- `0x1400139ae`: `UserCommunication::Connect() - The streaming filter received a new connection from a user mode application.`

## pseudocode

```c
__int64 __fastcall Streaming::Messaging::UserCommunication::Connect(PERESOURCE *this, struct _ERESOURCE *a2)
{
  bool v2; // di
  struct _ERESOURCE *v5; // rcx
  struct _ERESOURCE *v7; // rcx
  _QWORD *CurrentActivityID; // rax
  volatile signed __int32 *v9; // rbx
  _BYTE v10[8]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v11; // [rsp+28h] [rbp-30h]

  v2 = 0;
  if ( this[3] )
  {
    KeEnterCriticalRegion();
    v2 = ExAcquireResourceExclusiveLite(this[3], 1u) == 1;
  }
  if ( this[1] )
  {
    if ( v2 )
    {
      v5 = this[3];
      if ( v5 )
      {
        ExReleaseResourceLite(v5);
        KeLeaveCriticalRegion();
      }
    }
    return 3221225736LL;
  }
  else
  {
    this[1] = a2;
    if ( v2 )
    {
      v7 = this[3];
      if ( v7 )
      {
        ExReleaseResourceLite(v7);
        KeLeaveCriticalRegion();
      }
    }
    CurrentActivityID = (_QWORD *)Streaming::Utils::GetCurrentActivityID(v10);
    LogWrite(
      3,
      *CurrentActivityID,
      L"UserCommunication::Connect() - The streaming filter received a new connection from a user mode application.");
    v9 = v11;
    if ( v11 )
    {
      if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1400138fc  push    rbx
0x1400138fe  push    rbp
0x1400138ff  push    rsi
0x140013900  push    rdi
0x140013901  sub     rsp, 38h
0x140013905  xor     dil, dil
0x140013908  mov     rsi, rdx
0x14001390b  cmp     qword ptr [rcx+18h], 0
0x140013910  mov     rbx, rcx
0x140013913  jz      short loc_140013943
0x140013915  call    cs:__imp_KeEnterCriticalRegion
0x14001391c  nop     dword ptr [rax+rax+00h]
0x140013921  mov     rcx, [rbx+18h]; Resource
0x140013925  mov     ebp, 1
0x14001392a  mov     dl, bpl; Wait
0x14001392d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140013934  nop     dword ptr [rax+rax+00h]
0x140013939  cmp     al, bpl
0x14001393c  movzx   edi, dil
0x140013940  cmovz   edi, ebp
0x140013943  cmp     qword ptr [rbx+8], 0
0x140013948  jz      short loc_14001397A
0x14001394a  test    dil, dil
0x14001394d  jz      short loc_140013970
0x14001394f  mov     rcx, [rbx+18h]; Resource
0x140013953  test    rcx, rcx
0x140013956  jz      short loc_140013970
0x140013958  call    cs:__imp_ExReleaseResourceLite
0x14001395f  nop     dword ptr [rax+rax+00h]
0x140013964  call    cs:__imp_KeLeaveCriticalRegion
0x14001396b  nop     dword ptr [rax+rax+00h]
0x140013970  mov     eax, 0C0000108h
0x140013975  jmp     loc_140013A05
0x14001397a  mov     [rbx+8], rsi
0x14001397e  test    dil, dil
0x140013981  jz      short loc_1400139A4
0x140013983  mov     rcx, [rbx+18h]; Resource
0x140013987  test    rcx, rcx
0x14001398a  jz      short loc_1400139A4
0x14001398c  call    cs:__imp_ExReleaseResourceLite
0x140013993  nop     dword ptr [rax+rax+00h]
0x140013998  call    cs:__imp_KeLeaveCriticalRegion
0x14001399f  nop     dword ptr [rax+rax+00h]
0x1400139a4  lea     rcx, [rsp+58h+var_38]
0x1400139a9  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x1400139ae  lea     r8, aUsercommunicat_6; "UserCommunication::Connect() - The stre"...
0x1400139b5  mov     ecx, 3
0x1400139ba  mov     rdx, [rax]
0x1400139bd  call    LogWrite
0x1400139c2  mov     rbx, [rsp+58h+var_30]
0x1400139c7  test    rbx, rbx
0x1400139ca  jz      short loc_140013A03
0x1400139cc  or      edi, 0FFFFFFFFh
0x1400139cf  mov     eax, edi
0x1400139d1  lock xadd [rbx+8], eax
0x1400139d6  add     eax, edi
0x1400139d8  jnz     short loc_140013A03
0x1400139da  mov     rax, [rbx]
0x1400139dd  mov     rcx, rbx
0x1400139e0  mov     rax, [rax+8]
0x1400139e4  call    _guard_dispatch_icall
0x1400139e9  mov     eax, edi
0x1400139eb  lock xadd [rbx+0Ch], eax
0x1400139f0  add     eax, edi
0x1400139f2  jnz     short loc_140013A03
0x1400139f4  mov     rax, [rbx]
0x1400139f7  mov     rcx, rbx
0x1400139fa  mov     rax, [rax+10h]
0x1400139fe  call    _guard_dispatch_icall
0x140013a03  xor     eax, eax
0x140013a05  add     rsp, 38h
0x140013a09  pop     rdi
0x140013a0a  pop     rsi
0x140013a0b  pop     rbp
0x140013a0c  pop     rbx
0x140013a0d  retn
```
