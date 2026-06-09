# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)

- ea: `0x18004c2ac`
- end: `0x18004c48f`
- name: `??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U2@U1@U?$_tlgWrapperByVal@$03@@U3@U1@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@43AEBU?$_tlgWrapperByVal@$03@@535@Z`
- size: `483`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18005ecd0`
- `0x18005f4a0`
- `0x18005fc70`
- `0x18009b160`

## callees

- `0x18004c2ac`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004c43a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18004c43a`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
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
        int **a11,
        __int64 a12)
{
  __int64 v14; // rdx
  int *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  int *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  int *v21; // rcx
  int v22; // edx
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-B1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-99h] BYREF
  unsigned __int8 *v26; // [rsp+60h] [rbp-89h]
  int v27; // [rsp+68h] [rbp-81h]
  int v28; // [rsp+6Ch] [rbp-7Dh]
  int *v29; // [rsp+70h] [rbp-79h]
  int v30; // [rsp+78h] [rbp-71h]
  int v31; // [rsp+7Ch] [rbp-6Dh]
  __int64 v32; // [rsp+80h] [rbp-69h]
  __int64 v33; // [rsp+88h] [rbp-61h]
  __int64 v34; // [rsp+90h] [rbp-59h]
  __int64 v35; // [rsp+98h] [rbp-51h]
  int *v36; // [rsp+A0h] [rbp-49h]
  int v37; // [rsp+A8h] [rbp-41h]
  int v38; // [rsp+ACh] [rbp-3Dh]
  __int64 v39; // [rsp+B0h] [rbp-39h]
  __int64 v40; // [rsp+B8h] [rbp-31h]
  __int64 v41; // [rsp+C0h] [rbp-29h]
  __int64 v42; // [rsp+C8h] [rbp-21h]
  int *v43; // [rsp+D0h] [rbp-19h]
  int v44; // [rsp+D8h] [rbp-11h]
  int v45; // [rsp+DCh] [rbp-Dh]
  __int64 v46; // [rsp+E0h] [rbp-9h]
  __int64 v47; // [rsp+E8h] [rbp-1h]

  v46 = a12;
  v14 = -1;
  v47 = 4;
  v15 = *a11;
  if ( *a11 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    v17 = 2 * v16 + 2;
  }
  else
  {
    v15 = &dword_1800DB714;
    v17 = 2;
  }
  v44 = v17;
  v41 = a10;
  v39 = a9;
  v43 = v15;
  v45 = 0;
  v42 = 4;
  v18 = *a8;
  v40 = 4;
  if ( v18 )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    v20 = 2 * v19 + 2;
  }
  else
  {
    v18 = &dword_1800DB714;
    v20 = 2;
  }
  v37 = v20;
  v36 = v18;
  v38 = 0;
  v35 = 16;
  v34 = *a7;
  v33 = 16;
  v32 = *a6;
  v21 = *a5;
  if ( *a5 )
  {
    do
      ++v14;
    while ( *((_WORD *)v21 + v14) );
    v22 = 2 * v14 + 2;
  }
  else
  {
    v21 = &dword_1800DB714;
    v22 = 2;
  }
  *(_DWORD *)&EventDescriptor.Id = *a2 << 24;
  *(_DWORD *)&EventDescriptor.Level = *(unsigned __int16 *)(a2 + 1);
  EventDescriptor.Keyword = *(_QWORD *)(a2 + 3);
  UserData.Ptr = *(_QWORD *)(a1 + 8);
  v29 = v21;
  v30 = v22;
  v31 = 0;
  UserData.Size = *(unsigned __int16 *)UserData.Ptr;
  v27 = *(unsigned __int16 *)(a2 + 11);
  v26 = a2 + 11;
  UserData.Reserved = 2;
  v28 = 1;
  return EventWriteTransfer(*(_QWORD *)(a1 + 32), &EventDescriptor, 0, 0, 0xAu, &UserData);
}

```

## disassembly

```asm
0x18004c2ac  push    rbp
0x18004c2ae  lea     rbp, [rsp-17h]
0x18004c2b3  sub     rsp, 100h
0x18004c2ba  mov     rax, cs:__security_cookie
0x18004c2c1  xor     rax, rsp
0x18004c2c4  mov     [rbp+17h+var_10], rax
0x18004c2c8  mov     rax, [rbp+17h+arg_58]
0x18004c2cc  mov     r8, rdx
0x18004c2cf  mov     [rbp+17h+var_20], rax
0x18004c2d3  mov     r10, rcx
0x18004c2d6  mov     rax, [rbp+17h+arg_50]
0x18004c2da  xor     r11d, r11d
0x18004c2dd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004c2e1  mov     [rbp+17h+var_18], 4
0x18004c2e9  mov     rcx, [rax]
0x18004c2ec  test    rcx, rcx
0x18004c2ef  jz      loc_18004C45C
0x18004c2f5  mov     rax, rdx
0x18004c2f8  inc     rax
0x18004c2fb  cmp     [rcx+rax*2], r11w
0x18004c300  jnz     short loc_18004C2F8
0x18004c302  lea     eax, ds:2[rax*2]
0x18004c309  mov     [rbp+17h+var_28], eax
0x18004c30c  mov     rax, [rbp+17h+arg_48]
0x18004c310  mov     [rbp+17h+var_40], rax
0x18004c314  mov     rax, [rbp+17h+arg_40]
0x18004c318  mov     [rbp+17h+var_50], rax
0x18004c31c  mov     rax, [rbp+17h+arg_38]
0x18004c320  mov     [rbp+17h+var_30], rcx
0x18004c324  mov     [rbp+17h+var_24], r11d
0x18004c328  mov     [rbp+17h+var_38], 4
0x18004c330  mov     rcx, [rax]
0x18004c333  mov     [rbp+17h+var_48], 4
0x18004c33b  test    rcx, rcx
0x18004c33e  jz      loc_18004C46D
0x18004c344  mov     rax, rdx
0x18004c347  inc     rax
0x18004c34a  cmp     [rcx+rax*2], r11w
0x18004c34f  jnz     short loc_18004C347
0x18004c351  lea     eax, ds:2[rax*2]
0x18004c358  mov     [rbp+17h+var_58], eax
0x18004c35b  mov     rax, [rbp+17h+arg_30]
0x18004c35f  mov     [rbp+17h+var_60], rcx
0x18004c363  mov     [rbp+17h+var_54], r11d
0x18004c367  mov     [rbp+17h+var_68], 10h
0x18004c36f  mov     rcx, [rax]
0x18004c372  mov     rax, [rbp+17h+arg_28]
0x18004c376  mov     [rbp+17h+var_70], rcx
0x18004c37a  mov     [rbp+17h+var_78], 10h
0x18004c382  mov     rcx, [rax]
0x18004c385  mov     rax, [rbp+17h+arg_20]
0x18004c389  mov     [rbp+17h+var_80], rcx
0x18004c38d  mov     rcx, [rax]
0x18004c390  test    rcx, rcx
0x18004c393  jz      loc_18004C47E
0x18004c399  inc     rdx
0x18004c39c  cmp     [rcx+rdx*2], r11w
0x18004c3a1  jnz     short loc_18004C399
0x18004c3a3  lea     edx, ds:2[rdx*2]
0x18004c3aa  movzx   eax, byte ptr [r8]
0x18004c3ae  xor     r9d, r9d; RelatedActivityId
0x18004c3b1  shl     eax, 18h
0x18004c3b4  mov     dword ptr [rsp+100h+EventDescriptor.Id], eax
0x18004c3b8  movzx   eax, word ptr [r8+1]
0x18004c3bd  mov     dword ptr [rsp+100h+EventDescriptor.Level], eax
0x18004c3c1  mov     rax, [r8+3]
0x18004c3c5  mov     [rsp+100h+EventDescriptor.Keyword], rax
0x18004c3ca  mov     rax, [r10+8]
0x18004c3ce  mov     [rsp+100h+var_B0.Ptr], rax
0x18004c3d3  mov     [rbp+17h+var_90], rcx
0x18004c3d7  lea     rcx, [r8+0Bh]
0x18004c3db  mov     [rbp+17h+var_88], edx
0x18004c3de  xor     r8d, r8d; ActivityId
0x18004c3e1  mov     [rbp+17h+var_84], r11d
0x18004c3e5  lea     rdx, [rsp+100h+EventDescriptor]; EventDescriptor
0x18004c3ea  movzx   eax, word ptr [rax]
0x18004c3ed  mov     [rsp+100h+var_B0.Size], eax
0x18004c3f1  movzx   eax, word ptr [rcx]
0x18004c3f4  mov     [rsp+100h+var_98], eax
0x18004c3f8  lea     rax, _TraceLoggingMetadataEnd
0x18004c3ff  mov     [rsp+100h+var_A0], rcx
0x18004c404  lea     rcx, _TraceLoggingMetadata
0x18004c40b  sub     eax, ecx
0x18004c40d  mov     dword ptr [rsp+100h+var_B0.0Ch], 2
0x18004c415  mov     [rbp+17h+var_94], 1
0x18004c41c  mov     [rsp+100h+var_D0], eax
0x18004c420  mov     eax, [rsp+100h+var_D0]
0x18004c424  mov     rcx, [r10+20h]; RegHandle
0x18004c428  lea     rax, [rsp+100h+var_B0]
0x18004c42d  mov     [rsp+100h+UserData], rax; UserData
0x18004c432  mov     [rsp+100h+UserDataCount], 0Ah; UserDataCount
0x18004c43a  call    cs:__imp_EventWriteTransfer
0x18004c441  nop     dword ptr [rax+rax+00h]
0x18004c446  mov     rcx, [rbp+17h+var_10]
0x18004c44a  xor     rcx, rsp; StackCookie
0x18004c44d  call    __security_check_cookie
0x18004c452  add     rsp, 100h
0x18004c459  pop     rbp
0x18004c45a  retn
0x18004c45c  lea     rcx, dword_1800DB714
0x18004c463  mov     eax, 2
0x18004c468  jmp     loc_18004C309
0x18004c46d  lea     rcx, dword_1800DB714
0x18004c474  mov     eax, 2
0x18004c479  jmp     loc_18004C358
0x18004c47e  lea     rcx, dword_1800DB714
0x18004c485  mov     edx, 2
0x18004c48a  jmp     loc_18004C3AA
```
