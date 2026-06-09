# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180010c48`
- end: `0x180010cba`
- name: `?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `114`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800376a4`
- `0x180037954`
- `0x180038430`
- `0x180038660`

## callees

- `0x180010c48`
- `0x18002017c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010c5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010c5e`

## string_xrefs

- `0x180010c74`: `onecore\internal\sdk\inc\wil\opensource\wil\result.h`

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
0x180010c48  push    rbx; int
0x180010c4a  sub     rsp, 20h
0x180010c4e  cmp     dword ptr [rcx+138h], 0
0x180010c55  jz      short loc_180010CB3
0x180010c57  lea     rbx, [rcx+120h]
0x180010c5e  call    cs:__imp_GetCurrentThreadId
0x180010c65  nop     dword ptr [rax+rax+00h]
0x180010c6a  cmp     [rbx+18h], eax
0x180010c6d  jz      short loc_180010C8B
0x180010c6f  mov     rcx, [rsp+28h]; this
0x180010c74  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010c7b  mov     r9d, 8007029Ch; char *
0x180010c81  mov     edx, 3BEh; void *
0x180010c86  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180010c8b  and     dword ptr [rbx+18h], 0
0x180010c8f  mov     rcx, [rbx]
0x180010c92  mov     rax, [rcx]
0x180010c95  test    rax, rax
0x180010c98  jz      short loc_180010CAF
0x180010c9a  cmp     rax, rbx
0x180010c9d  jz      short loc_180010CA8
0x180010c9f  add     rax, 10h
0x180010ca3  mov     [rbx], rax
0x180010ca6  jmp     short loc_180010C8F
0x180010ca8  mov     rax, [rbx+10h]
0x180010cac  mov     [rcx], rax
0x180010caf  and     qword ptr [rbx], 0
0x180010cb3  add     rsp, 20h
0x180010cb7  pop     rbx
0x180010cb8  retn
```
