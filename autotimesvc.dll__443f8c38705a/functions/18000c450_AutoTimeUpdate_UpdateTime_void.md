# AutoTimeUpdate::UpdateTime(void)

- ea: `0x18000c450`
- end: `0x18000c5a2`
- name: `?UpdateTime@AutoTimeUpdate@@AEAA?AW4SyncResult@@XZ`
- size: `338`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000c3c8`

## callees

- `0x1800012f0`
- `0x1800015c0`
- `0x180002a70`
- `0x18000c20c`
- `0x18000c450`
- `0x18000c7ac`
- `0x18000cc10`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c4b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000c4b0`

## pseudocode

```c
__int64 __fastcall AutoTimeUpdate::UpdateTime(int *a1)
{
  unsigned int v2; // ebx
  __int64 v4; // rcx
  __int64 v5; // r8
  _BYTE v6[4]; // [rsp+50h] [rbp-9h] BYREF
  int v7; // [rsp+54h] [rbp-5h]
  __int64 v8; // [rsp+58h] [rbp-1h]
  __int64 v9; // [rsp+60h] [rbp+7h]
  __int128 *v10; // [rsp+68h] [rbp+Fh]
  __int64 v11; // [rsp+70h] [rbp+17h]
  __int128 v12; // [rsp+78h] [rbp+1Fh] BYREF
  __int128 v13; // [rsp+88h] [rbp+2Fh]
  __int64 v14; // [rsp+98h] [rbp+3Fh] BYREF

  v14 = WNF_CELL_NITZ_INFO;
  v6[0] = 0;
  v12 = 0;
  v13 = 0;
  if ( (int)wil::wnf_query_nothrow<WNF_CELL_NITZ_INFO_TYPE>(&v14, v6, &v12) < 0 || !v6[0] )
    return 5;
  if ( GetTickCount64() < (unsigned __int64)v13 || (unsigned int)(unsigned __int16)v12 + 2 < *a1 )
  {
    if ( (unsigned int)dword_18001C010 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 0x400000000100LL) )
    {
      v7 = *a1;
      v9 = v13;
      v10 = &v12;
      v8 = v5;
      v11 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        v4,
        (__int64)word_180016BE2);
    }
    return 4;
  }
  else
  {
    v2 = LastSyncInfo::SetTime(&v12, v13, **((unsigned int **)a1 + 1));
    if ( !v2 )
      LastSyncInfo::Publish(1, &v12, v13);
    return v2;
  }
}

```

## disassembly

```asm
0x18000c450  mov     [rsp-8+arg_8], rbx
0x18000c455  push    rbp
0x18000c456  lea     rbp, [rsp-57h]
0x18000c45b  sub     rsp, 0B0h
0x18000c462  mov     rax, cs:__security_cookie
0x18000c469  xor     rax, rsp
0x18000c46c  mov     [rbp+57h+var_10], rax
0x18000c470  mov     rax, cs:WNF_CELL_NITZ_INFO
0x18000c477  lea     r8, [rbp+57h+var_38]
0x18000c47b  xorps   xmm0, xmm0
0x18000c47e  mov     [rbp+57h+var_18], rax
0x18000c482  mov     rbx, rcx
0x18000c485  mov     [rbp+57h+var_60], 0
0x18000c489  lea     rcx, [rbp+57h+var_18]
0x18000c48d  lea     rdx, [rbp+57h+var_60]
0x18000c491  movups  [rbp+57h+var_38], xmm0
0x18000c495  movups  [rbp+57h+var_28], xmm0
0x18000c499  call    ??$wnf_query_nothrow@UWNF_CELL_NITZ_INFO_TYPE@@@wil@@YAJAEBU_WNF_STATE_NAME@@PEA_NPEAUWNF_CELL_NITZ_INFO_TYPE@@PEAUWNF_CHANGE_STAMP_STRUCT@0@@Z; wil::wnf_query_nothrow<WNF_CELL_NITZ_INFO_TYPE>(_WNF_STATE_NAME const &,bool *,WNF_CELL_NITZ_INFO_TYPE *,wil::WNF_CHANGE_STAMP_STRUCT *)
0x18000c49e  test    eax, eax
0x18000c4a0  js      loc_18000C580
0x18000c4a6  cmp     [rbp+57h+var_60], 0
0x18000c4aa  jz      loc_18000C580
0x18000c4b0  call    cs:__imp_GetTickCount64
0x18000c4b6  mov     rdx, qword ptr [rbp+57h+var_28]
0x18000c4ba  mov     r8, rax
0x18000c4bd  cmp     rax, rdx
0x18000c4c0  jb      short loc_18000C4FA
0x18000c4c2  movzx   ecx, word ptr [rbp+57h+var_38]
0x18000c4c6  add     ecx, 2
0x18000c4c9  cmp     ecx, [rbx]
0x18000c4cb  jb      short loc_18000C4FA
0x18000c4cd  mov     r8, [rbx+8]
0x18000c4d1  lea     rcx, [rbp+57h+var_38]
0x18000c4d5  mov     r8d, [r8]
0x18000c4d8  call    ?SetTime@LastSyncInfo@@SA?AW4SyncResult@@AEBU_SYSTEMTIME@@_KK@Z; LastSyncInfo::SetTime(_SYSTEMTIME const &,unsigned __int64,ulong)
0x18000c4dd  mov     ebx, eax
0x18000c4df  test    eax, eax
0x18000c4e1  jnz     short loc_18000C4F3
0x18000c4e3  mov     r8, qword ptr [rbp+57h+var_28]
0x18000c4e7  lea     rdx, [rbp+57h+var_38]
0x18000c4eb  lea     ecx, [rax+1]
0x18000c4ee  call    ?Publish@LastSyncInfo@@SAXW4Provider@@AEBU_SYSTEMTIME@@_K@Z; LastSyncInfo::Publish(Provider,_SYSTEMTIME const &,unsigned __int64)
0x18000c4f3  mov     eax, ebx
0x18000c4f5  jmp     loc_18000C585
0x18000c4fa  mov     eax, cs:dword_18001C010
0x18000c500  cmp     eax, 3
0x18000c503  jbe     short loc_18000C579
0x18000c505  mov     rdx, 400000000100h
0x18000c50f  lea     rcx, dword_18001C010
0x18000c516  call    _tlgKeywordOn
0x18000c51b  test    al, al
0x18000c51d  jz      short loc_18000C579
0x18000c51f  mov     eax, [rbx]
0x18000c521  lea     rdx, word_180016BE2
0x18000c528  mov     [rbp+57h+var_5C], eax
0x18000c52b  mov     rax, qword ptr [rbp+57h+var_28]
0x18000c52f  mov     [rbp+57h+var_50], rax
0x18000c533  lea     rax, [rbp+57h+var_38]
0x18000c537  mov     [rbp+57h+var_48], rax
0x18000c53b  lea     rax, [rbp+57h+var_5C]
0x18000c53f  mov     [rsp+0B0h+var_70], rax
0x18000c544  lea     rax, [rbp+57h+var_58]
0x18000c548  mov     [rsp+0B0h+var_78], rax
0x18000c54d  lea     rax, [rbp+57h+var_50]
0x18000c551  mov     [rsp+0B0h+var_80], rax
0x18000c556  lea     rax, [rbp+57h+var_48]
0x18000c55a  mov     [rsp+0B0h+var_88], rax
0x18000c55f  lea     rax, [rbp+57h+var_40]
0x18000c563  mov     [rsp+0B0h+var_90], rax
0x18000c568  mov     [rbp+57h+var_58], r8
0x18000c56c  mov     [rbp+57h+var_40], 1000000h
0x18000c574  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByRef@$0BA@@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByRef@$0BA@@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18000c579  mov     eax, 4
0x18000c57e  jmp     short loc_18000C585
0x18000c580  mov     eax, 5
0x18000c585  mov     rcx, [rbp+57h+var_10]
0x18000c589  xor     rcx, rsp; StackCookie
0x18000c58c  call    __security_check_cookie
0x18000c591  mov     rbx, [rsp+0B0h+arg_8]
0x18000c599  add     rsp, 0B0h
0x18000c5a0  pop     rbp
0x18000c5a1  retn
```
