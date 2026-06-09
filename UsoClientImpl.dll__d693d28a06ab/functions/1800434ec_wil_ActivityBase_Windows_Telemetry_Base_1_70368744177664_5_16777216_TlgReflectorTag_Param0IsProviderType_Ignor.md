# wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x1800434ec`
- end: `0x180043553`
- name: `?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `103`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18003e2a0`
- `0x18003e700`
- `0x18003ea9c`

## callees

- `0x180035ec8`
- `0x1800434ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043502`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043502`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 v1; // rbx
  void *v2; // rdx
  unsigned int v3; // r8d
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v1 = a1 + 288;
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v2, v3, (const char *)0x8007029CLL, v6);
    v4 = *(__int64 **)v1;
    *(_DWORD *)(v1 + 24) = 0;
    while ( 1 )
    {
      v5 = *v4;
      if ( !*v4 )
        break;
      if ( v5 == v1 )
      {
        *v4 = *(_QWORD *)(v1 + 16);
        break;
      }
      v4 = (__int64 *)(v5 + 16);
      *(_QWORD *)v1 = v5 + 16;
    }
    *(_QWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x1800434ec  push    rbx; int
0x1800434ee  sub     rsp, 20h
0x1800434f2  cmp     dword ptr [rcx+138h], 0
0x1800434f9  jz      short loc_18004354D
0x1800434fb  lea     rbx, [rcx+120h]
0x180043502  call    cs:__imp_GetCurrentThreadId
0x180043508  cmp     [rbx+18h], eax
0x18004350b  jz      short loc_18004351D
0x18004350d  mov     rcx, [rsp+28h]; this
0x180043512  mov     r9d, 8007029Ch; char *
0x180043518  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004351d  mov     rcx, [rbx]
0x180043520  mov     dword ptr [rbx+18h], 0
0x180043527  jmp     short loc_180043535
0x180043529  cmp     rax, rbx
0x18004352c  jz      short loc_18004353F
0x18004352e  lea     rcx, [rax+10h]
0x180043532  mov     [rbx], rcx
0x180043535  mov     rax, [rcx]
0x180043538  test    rax, rax
0x18004353b  jnz     short loc_180043529
0x18004353d  jmp     short loc_180043546
0x18004353f  mov     rax, [rbx+10h]
0x180043543  mov     [rcx], rax
0x180043546  mov     qword ptr [rbx], 0
0x18004354d  add     rsp, 20h
0x180043551  pop     rbx
0x180043552  retn
```
