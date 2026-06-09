# CleanupTargetedIo

- ea: `0x18005df50`
- end: `0x18005e001`
- name: `CleanupTargetedIo`
- size: `177`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18001bf00`
- `0x180052cb0`
- `0x180053000`
- `0x18005aa30`
- `0x18005b920`
- `0x18005c8e0`
- `0x18005e410`
- `0x180071ed0`

## callees

- `0x180009f20`
- `0x18005dc10`
- `0x18005df50`

## import_xrefs

- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x18005dfc0`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x18005dfc0`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x18005df8c`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x18005df8c`

## pseudocode

```c
void __fastcall CleanupTargetedIo(__int64 a1, PECP_LIST *a2, char a3)
{
  struct _ECP_LIST *v3; // r10
  unsigned int v6; // eax
  ULONG EcpContextSize; // [rsp+38h] [rbp+10h] BYREF
  PVOID EcpContext; // [rsp+48h] [rbp+20h] BYREF

  v3 = *a2;
  EcpContext = 0;
  EcpContextSize = 0;
  if ( v3 )
  {
    if ( !a1 || (*(_BYTE *)(a1 + 6) & 1) == 0 )
    {
      v6 = FsRtlRemoveExtraCreateParameter(v3, &FLTMGR_TIOCTRL_ECP_GUID, &EcpContext, &EcpContextSize);
      if ( (int)FltpDbgStatus(v6, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 654, 0) >= 0 )
      {
        *((_WORD *)EcpContext + 3) &= ~0x10u;
        FreeTargetedIoCtrl(EcpContext);
      }
    }
    if ( a3 )
    {
      FsRtlFreeExtraCreateParameterList(*a2);
      *a2 = 0;
    }
  }
}

```

## disassembly

```asm
0x18005df50  mov     [rsp+arg_0], rbx
0x18005df55  mov     [rsp+arg_10], rsi
0x18005df5a  push    rdi
0x18005df5b  sub     rsp, 20h
0x18005df5f  mov     r10, [rdx]
0x18005df62  xor     esi, esi
0x18005df64  mov     [rsp+28h+EcpContext], rsi
0x18005df69  movzx   edi, r8b
0x18005df6d  mov     [rsp+28h+EcpContextSize], esi
0x18005df71  mov     rbx, rdx
0x18005df74  test    r10, r10
0x18005df77  jz      short loc_18005DF9B
0x18005df79  test    rcx, rcx
0x18005df7c  jz      short loc_18005DFAC
0x18005df7e  test    byte ptr [rcx+6], 1
0x18005df82  jz      short loc_18005DFAC
0x18005df84  test    dil, dil
0x18005df87  jz      short loc_18005DF9B
0x18005df89  mov     rcx, [rbx]; EcpList
0x18005df8c  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x18005df93  nop     dword ptr [rax+rax+00h]
0x18005df98  mov     [rbx], rsi
0x18005df9b  mov     rbx, [rsp+28h+arg_0]
0x18005dfa0  mov     rsi, [rsp+28h+arg_10]
0x18005dfa5  add     rsp, 20h
0x18005dfa9  pop     rdi
0x18005dfaa  retn
0x18005dfac  lea     r9, [rsp+28h+EcpContextSize]; EcpContextSize
0x18005dfb1  mov     rcx, r10; EcpList
0x18005dfb4  lea     r8, [rsp+28h+EcpContext]; EcpContext
0x18005dfb9  lea     rdx, FLTMGR_TIOCTRL_ECP_GUID; EcpType
0x18005dfc0  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x18005dfc7  nop     dword ptr [rax+rax+00h]
0x18005dfcc  mov     r8d, 28Eh
0x18005dfd2  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005dfd9  mov     ecx, eax
0x18005dfdb  xor     r9d, r9d
0x18005dfde  call    FltpDbgStatus
0x18005dfe3  test    eax, eax
0x18005dfe5  js      short loc_18005DF84
0x18005dfe7  mov     rax, [rsp+28h+EcpContext]
0x18005dfec  mov     ecx, 0FFEFh
0x18005dff1  and     [rax+6], cx
0x18005dff5  mov     rcx, [rsp+28h+EcpContext]; EcpContext
0x18005dffa  call    FreeTargetedIoCtrl
0x18005dfff  jmp     short loc_18005DF84
```
