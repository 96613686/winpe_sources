# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180010b08`
- end: `0x180010b7a`
- name: `?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `114`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180036cc4`
- `0x180036f74`
- `0x180037a50`
- `0x180037c80`

## callees

- `0x180010b08`
- `0x1800213f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b1e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b1e`

## string_xrefs

- `0x180010b34`: `onecore\internal\sdk\inc\wil\opensource\wil\result.h`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  __int64 **v1; // rbx
  __int64 v2; // rax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v1 = (__int64 **)(a1 + 288);
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x3BE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result.h",
        (const char *)0x8007029CLL,
        v3);
    *((_DWORD *)v1 + 6) = 0;
    while ( 1 )
    {
      v2 = **v1;
      if ( !v2 )
        break;
      if ( (__int64 **)v2 == v1 )
      {
        **v1 = (__int64)v1[2];
        break;
      }
      *v1 = (__int64 *)(v2 + 16);
    }
    *v1 = 0;
  }
}

```

## disassembly

```asm
0x180010b08  push    rbx; int
0x180010b0a  sub     rsp, 20h
0x180010b0e  cmp     dword ptr [rcx+138h], 0
0x180010b15  jz      short loc_180010B73
0x180010b17  lea     rbx, [rcx+120h]
0x180010b1e  call    cs:__imp_GetCurrentThreadId
0x180010b25  nop     dword ptr [rax+rax+00h]
0x180010b2a  cmp     [rbx+18h], eax
0x180010b2d  jz      short loc_180010B4B
0x180010b2f  mov     rcx, [rsp+28h]; this
0x180010b34  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010b3b  mov     r9d, 8007029Ch; char *
0x180010b41  mov     edx, 3BEh; void *
0x180010b46  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180010b4b  and     dword ptr [rbx+18h], 0
0x180010b4f  mov     rcx, [rbx]
0x180010b52  mov     rax, [rcx]
0x180010b55  test    rax, rax
0x180010b58  jz      short loc_180010B6F
0x180010b5a  cmp     rax, rbx
0x180010b5d  jz      short loc_180010B68
0x180010b5f  add     rax, 10h
0x180010b63  mov     [rbx], rax
0x180010b66  jmp     short loc_180010B4F
0x180010b68  mov     rax, [rbx+10h]
0x180010b6c  mov     [rcx], rax
0x180010b6f  and     qword ptr [rbx], 0
0x180010b73  add     rsp, 20h
0x180010b77  pop     rbx
0x180010b78  retn
```
