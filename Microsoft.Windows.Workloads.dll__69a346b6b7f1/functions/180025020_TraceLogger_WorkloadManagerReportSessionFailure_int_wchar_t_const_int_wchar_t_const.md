# TraceLogger::WorkloadManagerReportSessionFailure<int &,wchar_t const *>(int &,wchar_t const * &&)

- ea: `0x180025020`
- end: `0x180025168`
- name: `??$WorkloadManagerReportSessionFailure@AEAHPEB_W@TraceLogger@@SAXAEAH$$QEAPEB_W@Z`
- size: `328`
- prototype: `int __fastcall(_DWORD *, const wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023620`

## callees

- `0x1800119b0`
- `0x180025020`
- `0x180034ef0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180025141`
- `ADVAPI32!EventWriteTransfer` at `0x180025141`

## pseudocode

```c
int __fastcall TraceLogger::WorkloadManagerReportSessionFailure<int &,wchar_t const *>(_DWORD *a1, const wchar_t **a2)
{
  const struct _tlgProvider_t *v4; // rax
  const struct _tlgProvider_t *v5; // r10
  const wchar_t *v6; // rdx
  __int64 v7; // rax
  int v9; // eax
  _DWORD v11[2]; // [rsp+30h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-58h] BYREF
  __int16 *v14; // [rsp+60h] [rbp-48h]
  int v15; // [rsp+68h] [rbp-40h]
  int v16; // [rsp+6Ch] [rbp-3Ch]
  _DWORD *v17; // [rsp+70h] [rbp-38h]
  __int64 v18; // [rsp+78h] [rbp-30h]
  const wchar_t *v19; // [rsp+80h] [rbp-28h]
  int v20; // [rsp+88h] [rbp-20h]
  int v21; // [rsp+8Ch] [rbp-1Ch]

  v4 = TraceLogger::Provider();
  v5 = v4;
  if ( *(_DWORD *)v4 > 5u )
  {
    v6 = *a2;
    v11[0] = *a1;
    if ( v6 )
    {
      v7 = -1;
      while ( v6[++v7] != 0 )
        ;
      v9 = 2 * v7 + 2;
    }
    else
    {
      v6 = &Src;
      v9 = 2;
    }
    v20 = v9;
    v21 = 0;
    v17 = v11;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = *((_QWORD *)v5 + 1);
    EventDescriptor.Keyword = 0;
    v19 = v6;
    v18 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v14 = &word_18004D596;
    UserData.Reserved = 2;
    v15 = 65;
    v16 = 1;
    v11[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    LODWORD(v4) = EventWriteTransfer(*((_QWORD *)v5 + 4), &EventDescriptor, 0, 0, 4u, &UserData);
  }
  return (int)v4;
}

```

## disassembly

```asm
0x180025020  mov     [rsp+arg_0], rbx
0x180025025  push    rdi
0x180025026  sub     rsp, 0A0h
0x18002502d  mov     rax, cs:__security_cookie
0x180025034  xor     rax, rsp
0x180025037  mov     [rsp+0A8h+var_18], rax
0x18002503f  mov     rbx, rdx
0x180025042  mov     rdi, rcx
0x180025045  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18002504a  mov     r10, rax
0x18002504d  cmp     dword ptr [rax], 5
0x180025050  jbe     loc_180025147
0x180025056  mov     rdx, [rbx]
0x180025059  mov     ecx, [rdi]
0x18002505b  mov     [rsp+0A8h+var_78], ecx
0x18002505f  test    rdx, rdx
0x180025062  jz      short loc_180025085
0x180025064  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002506b  nop     dword ptr [rax+rax+00h]
0x180025070  cmp     word ptr [rdx+rax*2+2], 0
0x180025076  lea     rax, [rax+1]
0x18002507a  jnz     short loc_180025070
0x18002507c  lea     eax, ds:2[rax*2]
0x180025083  jmp     short loc_180025091
0x180025085  lea     rdx, Src
0x18002508c  mov     eax, 2
0x180025091  mov     [rsp+0A8h+var_20], eax
0x180025098  xor     ecx, ecx
0x18002509a  mov     [rsp+0A8h+var_1C], ecx
0x1800250a1  lea     rax, [rsp+0A8h+var_78]
0x1800250a6  mov     [rsp+0A8h+var_38], rax
0x1800250ab  xor     r9d, r9d; RelatedActivityId
0x1800250ae  movzx   eax, cs:word_18004D58C
0x1800250b5  xor     r8d, r8d; ActivityId
0x1800250b8  mov     dword ptr [rsp+0A8h+EventDescriptor.Level], eax
0x1800250bc  mov     rax, [r10+8]
0x1800250c0  mov     [rsp+0A8h+var_58.Ptr], rax
0x1800250c5  mov     [rsp+0A8h+EventDescriptor.Keyword], rcx
0x1800250ca  lea     rcx, _TraceLoggingMetadata
0x1800250d1  mov     [rsp+0A8h+var_28], rdx
0x1800250d9  lea     rdx, [rsp+0A8h+EventDescriptor]; EventDescriptor
0x1800250de  mov     [rsp+0A8h+var_30], 4
0x1800250e7  mov     dword ptr [rsp+0A8h+EventDescriptor.Id], 0B000000h
0x1800250ef  movzx   eax, word ptr [rax]
0x1800250f2  mov     [rsp+0A8h+var_58.Size], eax
0x1800250f6  lea     rax, word_18004D596
0x1800250fd  mov     [rsp+0A8h+var_48], rax
0x180025102  lea     rax, _TraceLoggingMetadataEnd
0x180025109  sub     eax, ecx
0x18002510b  mov     dword ptr [rsp+0A8h+var_58.0Ch], 2
0x180025113  mov     [rsp+0A8h+var_40], 41h ; 'A'
0x18002511b  mov     [rsp+0A8h+var_3C], 1
0x180025123  mov     [rsp+0A8h+var_74], eax
0x180025127  mov     eax, [rsp+0A8h+var_74]
0x18002512b  mov     rcx, [r10+20h]; RegHandle
0x18002512f  lea     rax, [rsp+0A8h+var_58]
0x180025134  mov     [rsp+0A8h+UserData], rax; UserData
0x180025139  mov     [rsp+0A8h+UserDataCount], 4; UserDataCount
0x180025141  call    cs:__imp_EventWriteTransfer
0x180025147  mov     rcx, [rsp+0A8h+var_18]
0x18002514f  xor     rcx, rsp; StackCookie
0x180025152  call    __security_check_cookie
0x180025157  mov     rbx, [rsp+0A8h+arg_0]
0x18002515f  add     rsp, 0A0h
0x180025166  pop     rdi
0x180025167  retn
```
