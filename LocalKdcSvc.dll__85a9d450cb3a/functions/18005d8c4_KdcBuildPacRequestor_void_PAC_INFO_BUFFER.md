# KdcBuildPacRequestor(void *,_PAC_INFO_BUFFER * *)

- ea: `0x18005d8c4`
- end: `0x18005d985`
- name: `?KdcBuildPacRequestor@@YAJPEAXPEAPEAU_PAC_INFO_BUFFER@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(void *Src, struct _PAC_INFO_BUFFER **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004ab84`
- `0x18005c560`

## callees

- `0x1800038f0`
- `0x180010718`
- `0x1800107dc`
- `0x180010884`
- `0x18005a060`
- `0x18005d8c4`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18005d8ff`
- `ntdll!RtlLengthSid` at `0x18005d93c`
- `ntdll!RtlLengthSid` at `0x18005d8ff`
- `ntdll!RtlLengthSid` at `0x18005d93c`

## pseudocode

```c
__int64 __fastcall KdcBuildPacRequestor(void *Src, struct _PAC_INFO_BUFFER **a2)
{
  __int64 v4; // rax
  ULONG v5; // edi
  _DWORD *v6; // rax
  unsigned int v7; // ebx
  ULONG v8; // eax
  _BYTE v10[24]; // [rsp+20h] [rbp-18h] BYREF
  _DWORD *v11; // [rsp+50h] [rbp+18h] BYREF
  __int64 v12; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  v4 = lambda_2a70c627909d6c04886f368e19249c19_::_lambda_2a70c627909d6c04886f368e19249c19_(&v12, &v11);
  wil::scope_exit__lambda_2a70c627909d6c04886f368e19249c19___(v10, v4);
  v5 = RtlLengthSid(Src);
  v6 = MIDL_user_allocate(v5 + 16);
  v11 = v6;
  if ( v6 )
  {
    *v6 = 18;
    v11[1] = v5;
    *((_QWORD *)v11 + 1) = v11 + 4;
    v8 = RtlLengthSid(Src);
    memcpy_0(*((void **)v11 + 1), Src, v8);
    v7 = 0;
    *a2 = (struct _PAC_INFO_BUFFER *)v11;
    v11 = 0;
  }
  else
  {
    v7 = 60;
  }
  wil::details::lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5___::_lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5___(v10);
  return v7;
}

```

## disassembly

```asm
0x18005d8c4  mov     rax, rsp
0x18005d8c7  mov     [rax+8], rbx
0x18005d8cb  mov     [rax+10h], rsi
0x18005d8cf  push    rdi
0x18005d8d0  sub     rsp, 30h
0x18005d8d4  mov     rsi, rdx
0x18005d8d7  mov     qword ptr [rax+18h], 0
0x18005d8df  mov     rbx, rcx
0x18005d8e2  lea     rdx, [rax+18h]
0x18005d8e6  lea     rcx, [rax+20h]
0x18005d8ea  call    _lambda_2a70c627909d6c04886f368e19249c19____lambda_2a70c627909d6c04886f368e19249c19_
0x18005d8ef  mov     rdx, rax
0x18005d8f2  lea     rcx, [rsp+38h+var_18]
0x18005d8f7  call    wil__scope_exit__lambda_2a70c627909d6c04886f368e19249c19___
0x18005d8fc  mov     rcx, rbx; Sid
0x18005d8ff  call    cs:__imp_RtlLengthSid
0x18005d905  mov     edi, eax
0x18005d907  lea     ecx, [rax+10h]; size
0x18005d90a  call    MIDL_user_allocate
0x18005d90f  mov     [rsp+38h+arg_10], rax
0x18005d914  test    rax, rax
0x18005d917  jnz     short loc_18005D91E
0x18005d919  lea     ebx, [rax+3Ch]
0x18005d91c  jmp     short loc_18005D969
0x18005d91e  mov     dword ptr [rax], 12h
0x18005d924  mov     rax, [rsp+38h+arg_10]
0x18005d929  mov     [rax+4], edi
0x18005d92c  mov     rcx, [rsp+38h+arg_10]
0x18005d931  lea     rax, [rcx+10h]
0x18005d935  mov     [rcx+8], rax
0x18005d939  mov     rcx, rbx; Sid
0x18005d93c  call    cs:__imp_RtlLengthSid
0x18005d942  mov     rcx, [rsp+38h+arg_10]
0x18005d947  mov     rdx, rbx; Src
0x18005d94a  mov     r8d, eax; Size
0x18005d94d  mov     rcx, [rcx+8]; void *
0x18005d951  call    memcpy_0
0x18005d956  mov     rax, [rsp+38h+arg_10]
0x18005d95b  xor     ebx, ebx
0x18005d95d  mov     [rsi], rax
0x18005d960  mov     [rsp+38h+arg_10], 0
0x18005d969  lea     rcx, [rsp+38h+var_18]
0x18005d96e  call    wil__details__lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5______lambda_call__lambda_eb3c6cf637a6f9bf09df8801c3663cc5___
0x18005d973  mov     rsi, [rsp+38h+arg_8]
0x18005d978  mov     eax, ebx
0x18005d97a  mov     rbx, [rsp+38h+arg_0]
0x18005d97f  add     rsp, 30h
0x18005d983  pop     rdi
0x18005d984  retn
```
