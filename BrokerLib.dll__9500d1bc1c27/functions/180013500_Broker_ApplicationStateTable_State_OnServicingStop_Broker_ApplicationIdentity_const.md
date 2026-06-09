# Broker::ApplicationStateTable::State::OnServicingStop(Broker::ApplicationIdentity const *)

- ea: `0x180013500`
- end: `0x18001358d`
- name: `?OnServicingStop@State@ApplicationStateTable@Broker@@QEAA_NPEBUApplicationIdentity@3@@Z`
- size: `141`
- prototype: `bool __fastcall(Broker::ApplicationStateTable::State *__hidden this, const struct Broker::ApplicationIdentity *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180008554`

## callees

- `0x18000a970`
- `0x180013500`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001351e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001351e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001357c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001357c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013524`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013524`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Broker::ApplicationStateTable::State::OnServicingStop(
        Broker::ApplicationStateTable::State *this,
        const struct Broker::ApplicationIdentity *a2)
{
  char *v4; // rbp
  _BYTE *v5; // rax
  char v6; // di
  const unsigned __int16 *v7; // rdx
  bool v8; // bl

  v4 = (char *)this + 144;
  RtlAcquireSRWLockExclusive((char *)this + 144);
  GetCurrentThreadId();
  v5 = (char *)this + 137;
  v6 = *((_BYTE *)this + 136) && *v5;
  *v5 = 1;
  if ( a2 )
  {
    v7 = (const unsigned __int16 *)((char *)a2 + 56);
    if ( *((_QWORD *)a2 + 10) > 7u )
      v7 = *(const unsigned __int16 **)v7;
    Broker::ApplicationIdentity::SetPackageFullName(this, v7);
  }
  v8 = v6 != *((_BYTE *)this + 136);
  RtlReleaseSRWLockExclusive(v4);
  return v8;
}

```

## disassembly

```asm
0x180013500  push    rbx
0x180013502  push    rbp
0x180013503  push    rsi
0x180013504  push    rdi
0x180013505  sub     rsp, 38h
0x180013509  mov     rsi, rdx
0x18001350c  mov     rbx, rcx
0x18001350f  lea     rbp, [rcx+90h]
0x180013516  mov     [rsp+58h+var_38], rbp
0x18001351b  mov     rcx, rbp
0x18001351e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180013524  call    cs:__imp_GetCurrentThreadId
0x18001352a  mov     [rsp+58h+var_2C], eax
0x18001352e  mov     [rsp+58h+var_30], 1
0x180013533  lea     rax, [rbx+89h]
0x18001353a  cmp     byte ptr [rbx+88h], 0
0x180013541  jz      short loc_18001354D
0x180013543  cmp     byte ptr [rax], 0
0x180013546  jz      short loc_18001354D
0x180013548  mov     dil, 1
0x18001354b  jmp     short loc_180013550
0x18001354d  xor     dil, dil
0x180013550  mov     byte ptr [rax], 1
0x180013553  test    rsi, rsi
0x180013556  jz      short loc_18001356F
0x180013558  lea     rdx, [rsi+38h]
0x18001355c  cmp     qword ptr [rdx+18h], 7
0x180013561  jbe     short loc_180013566
0x180013563  mov     rdx, [rdx]; unsigned __int16 *
0x180013566  mov     rcx, rbx; this
0x180013569  call    ?SetPackageFullName@ApplicationIdentity@Broker@@QEAAXQEBG@Z; Broker::ApplicationIdentity::SetPackageFullName(ushort const * const)
0x18001356e  nop
0x18001356f  cmp     dil, [rbx+88h]
0x180013576  setnz   bl
0x180013579  mov     rcx, rbp
0x18001357c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180013582  mov     al, bl
0x180013584  add     rsp, 38h
0x180013588  pop     rdi
0x180013589  pop     rsi
0x18001358a  pop     rbp
0x18001358b  pop     rbx
0x18001358c  retn
```
