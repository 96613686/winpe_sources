# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18004ac70`
- end: `0x18004ae14`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U2@U1@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@43AEBU?$_tlgWrapperByVal@$03@@55@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001e63c`

## callees

- `0x18004ac70`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004add0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004add0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        int **a5,
        __int64 *a6,
        __int64 *a7,
        int **a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  int *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  bool v16; // zf
  int v17; // ecx
  int *v18; // rdx
  int v19; // eax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-99h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int8 *v23; // [rsp+60h] [rbp-71h]
  int v24; // [rsp+68h] [rbp-69h]
  int v25; // [rsp+6Ch] [rbp-65h]
  int *v26; // [rsp+70h] [rbp-61h]
  int v27; // [rsp+78h] [rbp-59h]
  int v28; // [rsp+7Ch] [rbp-55h]
  __int64 v29; // [rsp+80h] [rbp-51h]
  __int64 v30; // [rsp+88h] [rbp-49h]
  __int64 v31; // [rsp+90h] [rbp-41h]
  __int64 v32; // [rsp+98h] [rbp-39h]
  int *v33; // [rsp+A0h] [rbp-31h]
  int v34; // [rsp+A8h] [rbp-29h]
  int v35; // [rsp+ACh] [rbp-25h]
  __int64 v36; // [rsp+B0h] [rbp-21h]
  __int64 v37; // [rsp+B8h] [rbp-19h]
  __int64 v38; // [rsp+C0h] [rbp-11h]
  __int64 v39; // [rsp+C8h] [rbp-9h]
  __int64 v40; // [rsp+D0h] [rbp-1h]
  __int64 v41; // [rsp+D8h] [rbp+7h]

  v40 = a11;
  v38 = a10;
  v36 = a9;
  v41 = 4;
  v39 = 4;
  v37 = 4;
  v13 = *a8;
  v14 = -1;
  if ( *a8 )
  {
    v15 = -1;
    do
      v16 = *((_WORD *)v13 + ++v15) == 0;
    while ( !v16 );
    v17 = 2 * v15 + 2;
  }
  else
  {
    v13 = &dword_1800DB714;
    v17 = 2;
  }
  v34 = v17;
  v33 = v13;
  v35 = 0;
  v32 = 16;
  v31 = *a7;
  v30 = 16;
  v29 = *a6;
  v18 = *a5;
  if ( *a5 )
  {
    do
      v16 = *((_WORD *)v18 + ++v14) == 0;
    while ( !v16 );
    v19 = 2 * v14 + 2;
  }
  else
  {
    v18 = &dword_1800DB714;
    v19 = 2;
  }
  v27 = v19;
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v26 = v18;
  v28 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v24 = *(unsigned __int16 *)(a2 + 11);
  v23 = a2 + 11;
  UserData.Reserved = 2;
  v25 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 9u, &UserData);
}

```

## disassembly

```asm
0x18004ac70  push    rbp
0x18004ac72  lea     rbp, [rsp-1Fh]
0x18004ac77  sub     rsp, 0F0h
0x18004ac7e  mov     rax, cs:__security_cookie
0x18004ac85  xor     rax, rsp
0x18004ac88  mov     [rbp+1Fh+var_10], rax
0x18004ac8c  mov     rax, [rbp+1Fh+arg_50]
0x18004ac90  mov     r8, rdx
0x18004ac93  mov     [rbp+1Fh+var_20], rax
0x18004ac97  xor     r9d, r9d; RelatedActivityId
0x18004ac9a  mov     rax, [rbp+1Fh+arg_48]
0x18004ac9e  mov     r10, rcx
0x18004aca1  mov     [rbp+1Fh+var_30], rax
0x18004aca5  mov     rax, [rbp+1Fh+arg_40]
0x18004aca9  mov     [rbp+1Fh+var_40], rax
0x18004acad  mov     rax, [rbp+1Fh+arg_38]
0x18004acb1  mov     [rbp+1Fh+var_18], 4
0x18004acb9  mov     [rbp+1Fh+var_28], 4
0x18004acc1  mov     [rbp+1Fh+var_38], 4
0x18004acc9  mov     rdx, [rax]
0x18004accc  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004acd3  test    rdx, rdx
0x18004acd6  jz      loc_18004ADF2
0x18004acdc  mov     rcx, rax
0x18004acdf  nop
0x18004ace0  cmp     [rdx+rcx*2+2], r9w
0x18004ace6  lea     rcx, [rcx+1]
0x18004acea  jnz     short loc_18004ACE0
0x18004acec  lea     ecx, ds:2[rcx*2]
0x18004acf3  mov     [rbp+1Fh+var_48], ecx
0x18004acf6  mov     rcx, [rbp+1Fh+arg_30]
0x18004acfa  mov     [rbp+1Fh+var_50], rdx
0x18004acfe  mov     [rbp+1Fh+var_44], r9d
0x18004ad02  mov     [rbp+1Fh+var_58], 10h
0x18004ad0a  mov     rdx, [rcx]
0x18004ad0d  mov     rcx, [rbp+1Fh+arg_28]
0x18004ad11  mov     [rbp+1Fh+var_60], rdx
0x18004ad15  mov     [rbp+1Fh+var_68], 10h
0x18004ad1d  mov     rdx, [rcx]
0x18004ad20  mov     rcx, [rbp+1Fh+arg_20]
0x18004ad24  mov     [rbp+1Fh+var_70], rdx
0x18004ad28  mov     rdx, [rcx]
0x18004ad2b  test    rdx, rdx
0x18004ad2e  jz      loc_18004AE03
0x18004ad34  cmp     [rdx+rax*2+2], r9w
0x18004ad3a  lea     rax, [rax+1]
0x18004ad3e  jnz     short loc_18004AD34
0x18004ad40  lea     eax, ds:2[rax*2]
0x18004ad47  mov     [rbp+1Fh+var_78], eax
0x18004ad4a  lea     rcx, [r8+0Bh]
0x18004ad4e  movzx   eax, byte ptr [r8]
0x18004ad52  shl     eax, 18h
0x18004ad55  mov     dword ptr [rsp+0F0h+EventDescriptor.Id], eax
0x18004ad59  movzx   eax, word ptr [r8+1]
0x18004ad5e  mov     dword ptr [rsp+0F0h+EventDescriptor.Level], eax
0x18004ad62  mov     rax, [r8+3]
0x18004ad66  xor     r8d, r8d; ActivityId
0x18004ad69  mov     [rsp+0F0h+EventDescriptor.Keyword], rax
0x18004ad6e  mov     rax, [r10+8]
0x18004ad72  mov     [rsp+0F0h+var_A0.Ptr], rax
0x18004ad77  mov     [rbp+1Fh+var_80], rdx
0x18004ad7b  lea     rdx, [rsp+0F0h+EventDescriptor]; EventDescriptor
0x18004ad80  mov     [rbp+1Fh+var_74], r9d
0x18004ad84  movzx   eax, word ptr [rax]
0x18004ad87  mov     [rbp+1Fh+var_A0.Size], eax
0x18004ad8a  movzx   eax, word ptr [rcx]
0x18004ad8d  mov     [rbp+1Fh+var_88], eax
0x18004ad90  lea     rax, _TraceLoggingMetadataEnd
0x18004ad97  mov     [rbp+1Fh+var_90], rcx
0x18004ad9b  lea     rcx, _TraceLoggingMetadata
0x18004ada2  sub     eax, ecx
0x18004ada4  mov     dword ptr [rbp+1Fh+var_A0.0Ch], 2
0x18004adab  mov     [rbp+1Fh+var_84], 1
0x18004adb2  mov     [rsp+0F0h+var_C0], eax
0x18004adb6  mov     eax, [rsp+0F0h+var_C0]
0x18004adba  mov     rcx, [r10+20h]; RegHandle
0x18004adbe  lea     rax, [rsp+0F0h+var_A0]
0x18004adc3  mov     [rsp+0F0h+UserData], rax; UserData
0x18004adc8  mov     [rsp+0F0h+UserDataCount], 9; UserDataCount
0x18004add0  call    cs:__imp_EventWriteTransfer
0x18004add7  nop     dword ptr [rax+rax+00h]
0x18004addc  mov     rcx, [rbp+1Fh+var_10]
0x18004ade0  xor     rcx, rsp; StackCookie
0x18004ade3  call    __security_check_cookie
0x18004ade8  add     rsp, 0F0h
0x18004adef  pop     rbp
0x18004adf0  retn
0x18004adf2  lea     rdx, dword_1800DB714
0x18004adf9  mov     ecx, 2
0x18004adfe  jmp     loc_18004ACF3
0x18004ae03  lea     rdx, dword_1800DB714
0x18004ae0a  mov     eax, 2
0x18004ae0f  jmp     loc_18004AD47
```
