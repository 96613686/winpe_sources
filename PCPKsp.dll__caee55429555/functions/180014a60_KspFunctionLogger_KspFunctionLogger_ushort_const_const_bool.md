# KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)

- ea: `0x180014a60`
- end: `0x180014bbf`
- name: `??0KspFunctionLogger@@QEAA@QEBG_N@Z`
- size: `351`
- prototype: `KspFunctionLogger *__fastcall(KspFunctionLogger *__hidden this, const unsigned __int16 *const, bool)`
- caller_count: `290`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d750`
- `0x18000dc90`
- `0x18000f240`
- `0x1800116d0`
- `0x180011c60`
- `0x180012640`
- `0x1800133f0`
- `0x1800138e0`
- `0x180013b00`
- `0x180013d60`
- `0x180014590`
- `0x180014bd0`
- `0x180015ac0`
- `0x180018d8c`
- `0x180018e20`
- `0x180019ed4`
- `0x18001adf0`
- `0x18001b050`
- `0x18001b4a0`
- `0x18001b8f0`
- `0x18001d590`
- `0x18001fed4`
- `0x180021b7c`
- `0x180023f98`
- `0x1800249d8`
- `0x180026830`
- `0x180026948`
- `0x180026b90`
- `0x180026e30`
- `0x180027210`
- `0x180027670`
- `0x18002809c`
- `0x180028bb0`
- `0x180028cd8`
- `0x180028f24`
- `0x1800293e0`
- `0x180029700`
- `0x18002a0b0`
- `0x18002a820`
- `0x18002acd4`
- `0x18002b50c`
- `0x18002b6e0`
- `0x18002c5a8`
- `0x18002c830`
- `0x18002d934`
- `0x18002dfe0`
- `0x18002e900`
- `0x18002f374`
- `0x18002f774`
- `0x18002fd90`

## callees

- `0x180014a60`
- `0x18003cf80`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014b8e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180014b8e`

## pseudocode

```c
KspFunctionLogger *__fastcall KspFunctionLogger::KspFunctionLogger(
        KspFunctionLogger *this,
        const unsigned __int16 *const a2,
        char a3)
{
  __int64 v4; // r10
  int *v5; // rcx
  __int64 v6; // rax
  int v8; // eax
  __int64 v10; // [rsp+38h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-58h] BYREF
  char *v13; // [rsp+60h] [rbp-48h]
  int v14; // [rsp+68h] [rbp-40h]
  int v15; // [rsp+6Ch] [rbp-3Ch]
  __int64 *v16; // [rsp+70h] [rbp-38h]
  __int64 v17; // [rsp+78h] [rbp-30h]
  int *v18; // [rsp+80h] [rbp-28h]
  int v19; // [rsp+88h] [rbp-20h]
  int v20; // [rsp+8Ch] [rbp-1Ch]

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 16) = a3;
  v4 = *((_QWORD *)KspDebugProvider::Instance() + 1);
  if ( *(_DWORD *)v4 > 5u )
  {
    v5 = *(int **)this;
    v10 = 0x1000000;
    if ( v5 )
    {
      v6 = -1;
      while ( *((_WORD *)v5 + ++v6) != 0 )
        ;
      v8 = 2 * v6 + 2;
    }
    else
    {
      v5 = &dword_1800DB714;
      v8 = 2;
    }
    v19 = v8;
    v18 = v5;
    v16 = &v10;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *(_QWORD *)(v4 + 8);
    v20 = 0;
    v17 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v13 = byte_1800F9F15;
    UserData.Reserved = 2;
    v14 = 39;
    v15 = 1;
    EventWriteTransfer(*(_QWORD *)(v4 + 32), &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return this;
}

```

## disassembly

```asm
0x180014a60  mov     [rsp+arg_8], rbx
0x180014a65  push    rdi
0x180014a66  sub     rsp, 0A0h
0x180014a6d  mov     rax, cs:__security_cookie
0x180014a74  xor     rax, rsp
0x180014a77  mov     [rsp+0A8h+var_18], rax
0x180014a7f  xor     edi, edi
0x180014a81  mov     [rcx], rdx
0x180014a84  mov     [rcx+8], rdi
0x180014a88  mov     rbx, rcx
0x180014a8b  mov     [rcx+10h], r8b
0x180014a8f  call    ?Instance@KspDebugProvider@@KAPEAV1@XZ; KspDebugProvider::Instance(void)
0x180014a94  mov     r10, [rax+8]
0x180014a98  mov     eax, [r10]
0x180014a9b  cmp     eax, 5
0x180014a9e  jbe     loc_180014B9A
0x180014aa4  mov     rcx, [rbx]
0x180014aa7  mov     [rsp+0A8h+var_70], 1000000h
0x180014ab0  test    rcx, rcx
0x180014ab3  jz      short loc_180014AD4
0x180014ab5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180014abc  nop     dword ptr [rax+00h]
0x180014ac0  cmp     [rcx+rax*2+2], di
0x180014ac5  lea     rax, [rax+1]
0x180014ac9  jnz     short loc_180014AC0
0x180014acb  lea     eax, ds:2[rax*2]
0x180014ad2  jmp     short loc_180014AE0
0x180014ad4  lea     rcx, dword_1800DB714
0x180014adb  mov     eax, 2
0x180014ae0  mov     [rsp+0A8h+var_20], eax
0x180014ae7  lea     rdx, _TraceLoggingMetadataEnd
0x180014aee  mov     [rsp+0A8h+var_28], rcx
0x180014af6  lea     rax, [rsp+0A8h+var_70]
0x180014afb  mov     [rsp+0A8h+var_38], rax
0x180014b00  xor     r9d, r9d; RelatedActivityId
0x180014b03  movzx   eax, cs:word_1800F9F0B
0x180014b0a  xor     r8d, r8d; ActivityId
0x180014b0d  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x180014b11  mov     rax, [r10+8]
0x180014b15  mov     [rsp+0A8h+var_58.Ptr], rax
0x180014b1a  mov     [rsp+0A8h+var_1C], edi
0x180014b21  mov     [rsp+0A8h+var_30], 8
0x180014b2a  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], 0B000000h
0x180014b32  mov     [rsp+0A8h+EventDescriptor.Keyword], rdi
0x180014b37  movzx   eax, word ptr [rax]
0x180014b3a  mov     [rsp+0A8h+var_58.Size], eax
0x180014b3e  lea     rax, byte_1800F9F15
0x180014b45  mov     [rsp+0A8h+var_48], rax
0x180014b4a  lea     rax, _TraceLoggingMetadata
0x180014b51  sub     edx, eax
0x180014b53  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x180014b5b  mov     [rsp+0A8h+var_40], 27h ; '''
0x180014b63  lea     rax, [rsp+0A8h+var_58]
0x180014b68  mov     [rsp+0A8h+var_3C], 1
0x180014b70  mov     [rsp+0A8h+var_78], edx
0x180014b74  mov     edx, [rsp+0A8h+var_78]
0x180014b78  mov     rcx, [r10+20h]; RegHandle
0x180014b7c  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x180014b81  mov     [rsp+0A8h+UserData], rax; UserData
0x180014b86  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x180014b8e  call    cs:__imp_EventWriteTransfer
0x180014b95  nop     dword ptr [rax+rax+00h]
0x180014b9a  mov     rax, rbx
0x180014b9d  mov     rcx, [rsp+0A8h+var_18]
0x180014ba5  xor     rcx, rsp; StackCookie
0x180014ba8  call    __security_check_cookie
0x180014bad  mov     rbx, [rsp+0A8h+arg_8]
0x180014bb5  add     rsp, 0A0h
0x180014bbc  pop     rdi
0x180014bbd  retn
```
