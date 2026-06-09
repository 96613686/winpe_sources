# wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x1800108d0`
- end: `0x180010949`
- name: `?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `121`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f840`
- `0x180010950`

## callees

- `0x1800108d0`
- `0x180010c70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800108e9`
- `KERNEL32!GetCurrentThreadId` at `0x1800108e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  int v1; // ebx
  __int64 v2; // rbx
  void *v3; // rdx
  unsigned int v4; // r8d
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_DWORD *)(a1 + 312) )
  {
    v7 = v1;
    v2 = a1 + 288;
    if ( *(_DWORD *)(a1 + 312) != GetCurrentThreadId() )
      wil::details::in1diag3::Log_Hr(retaddr, v3, v4, (const char *)0x8007029CLL, v7);
    v5 = *(__int64 **)v2;
    *(_DWORD *)(v2 + 24) = 0;
    v6 = *v5;
    if ( *v5 )
    {
      while ( v6 != v2 )
      {
        v5 = (__int64 *)(v6 + 16);
        *(_QWORD *)v2 = v6 + 16;
        v6 = *(_QWORD *)(v6 + 16);
        if ( !v6 )
        {
          *(_QWORD *)v2 = 0;
          return;
        }
      }
      *v5 = *(_QWORD *)(v2 + 16);
    }
    *(_QWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x1800108d0  sub     rsp, 28h
0x1800108d4  cmp     dword ptr [rcx+138h], 0
0x1800108db  jz      short loc_180010944
0x1800108dd  mov     qword ptr [rsp+28h+var_8], rbx; int
0x1800108e2  lea     rbx, [rcx+120h]
0x1800108e9  call    cs:__imp_GetCurrentThreadId
0x1800108ef  cmp     [rbx+18h], eax
0x1800108f2  jz      short loc_180010904
0x1800108f4  mov     rcx, [rsp+28h]; this
0x1800108f9  mov     r9d, 8007029Ch; char *
0x1800108ff  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180010904  mov     rcx, [rbx]
0x180010907  xor     edx, edx
0x180010909  mov     [rbx+18h], edx
0x18001090c  mov     rax, [rcx]
0x18001090f  test    rax, rax
0x180010912  jz      short loc_18001093C
0x180010914  cmp     rax, rbx
0x180010917  jz      short loc_180010935
0x180010919  lea     rcx, [rax+10h]
0x18001091d  mov     [rbx], rcx
0x180010920  mov     rax, [rcx]
0x180010923  test    rax, rax
0x180010926  jnz     short loc_180010914
0x180010928  mov     [rbx], rdx
0x18001092b  mov     rbx, qword ptr [rsp+28h+var_8]
0x180010930  add     rsp, 28h
0x180010934  retn
0x180010935  mov     rax, [rbx+10h]
0x180010939  mov     [rcx], rax
0x18001093c  mov     [rbx], rdx
0x18001093f  mov     rbx, qword ptr [rsp+28h+var_8]
0x180010944  add     rsp, 28h
0x180010948  retn
```
