# CWwanDataExecutorState::OnCanIMSIChange(WNF_CELL_IMSI_TYPE const *)

- ea: `0x18003cb2c`
- end: `0x18003cd20`
- name: `?OnCanIMSIChange@CWwanDataExecutorState@@IEAAXPEBUWNF_CELL_IMSI_TYPE@@@Z`
- size: `500`
- prototype: `void __fastcall(CWwanDataExecutorState *__hidden this, const struct WNF_CELL_IMSI_TYPE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180065290`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x18000f0f4`
- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x18003cb2c`
- `0x1800424c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003cb75`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003cb75`

## string_xrefs

- `0x18003cb98`: `(Modem {%s} EXEC %d): IMSI change notification (cImsi %d) while can is deconfigured.`
- `0x18003cba3`: `CWwanDataExecutorState::OnCanIMSIChange`
- `0x18003cbc9`: `CWwanDataExecutorState::OnCanIMSIChange`
- `0x18003cbff`: `CWwanDataExecutorState::OnCanIMSIChange`
- `0x18003cc25`: `CWwanDataExecutorState::OnCanIMSIChange`
- `0x18003ccd4`: `CWwanDataExecutorState::OnCanIMSIChange`
- `0x18003cbbe`: `(Modem {%s} EXEC %d): cImsi %d is not equal to number of configured lines (%d)`
- `0x18003cbf4`: `(Modem {%s} EXEC %d): IMSI is notified again while IMSI is already obtained (cIMsi %d IMSI0 %s)`
- `0x18003cc1a`: `(Modem {%s} EXEC %d): IMSI obtained (cIMsi %d)`
- `0x18003cccd`: `Work-around for bug 995415 - copy IMSI (%ws) to subscriberId`

## pseudocode

```c
void __fastcall CWwanDataExecutorState::OnCanIMSIChange(
        CWwanDataExecutorState *this,
        const struct WNF_CELL_IMSI_TYPE *a2)
{
  int v4; // ecx
  int v5; // eax
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  int v9; // [rsp+20h] [rbp-98h]
  int v10; // [rsp+20h] [rbp-98h]
  int v11; // [rsp+20h] [rbp-98h]
  int v12; // [rsp+20h] [rbp-98h]
  int v13; // [rsp+28h] [rbp-90h]
  int v14; // [rsp+28h] [rbp-90h]
  int v15; // [rsp+28h] [rbp-90h]
  int v16; // [rsp+28h] [rbp-90h]
  int v17; // [rsp+30h] [rbp-88h]
  OLECHAR sz[40]; // [rsp+40h] [rbp-78h] BYREF

  memset_0(sz, 0, 0x4Au);
  StringFromGUID2((const GUID *const)((char *)this + 12552), sz, 37);
  v4 = *((_DWORD *)this + 3186);
  if ( v4 )
  {
    if ( v4 == *(_DWORD *)a2 )
    {
      if ( *((_DWORD *)this + 3656) )
      {
        v15 = *((_DWORD *)this + 3186);
        v11 = *((_DWORD *)this + 3143);
        WwanLog::Warning(
          "CWwanDataExecutorState::OnCanIMSIChange",
          0,
          L"(Modem {%s} EXEC %d): IMSI is notified again while IMSI is already obtained (cIMsi %d IMSI0 %s)",
          sz,
          v11,
          v15,
          (char *)this + 13040);
      }
      else
      {
        v16 = *(_DWORD *)a2;
        v12 = *((_DWORD *)this + 3143);
        WwanLog::Info(
          "CWwanDataExecutorState::OnCanIMSIChange",
          0,
          L"(Modem {%s} EXEC %d): IMSI obtained (cIMsi %d)",
          sz,
          v12,
          v16);
        v5 = *((_DWORD *)this + 3275);
        v6 = *(_OWORD *)((char *)this + 13052);
        *((_OWORD *)this + 819) = *(_OWORD *)((char *)this + 13036);
        v7 = *(_OWORD *)((char *)this + 13068);
        *((_OWORD *)this + 820) = v6;
        v8 = *(_OWORD *)((char *)this + 13084);
        *((_OWORD *)this + 821) = v7;
        *((_OWORD *)this + 822) = v8;
        *((_DWORD *)this + 3292) = v5;
        *(_OWORD *)((char *)this + 13036) = *(_OWORD *)a2;
        *(_OWORD *)((char *)this + 13052) = *((_OWORD *)a2 + 1);
        *(_OWORD *)((char *)this + 13068) = *((_OWORD *)a2 + 2);
        *(_OWORD *)((char *)this + 13084) = *((_OWORD *)a2 + 3);
        *((_DWORD *)this + 3275) = *((_DWORD *)a2 + 16);
        *((_DWORD *)this + 3656) = 1;
        if ( !*((_WORD *)this + 7124) )
        {
          WwanLog::Info(
            "CWwanDataExecutorState::OnCanIMSIChange",
            0,
            L"Work-around for bug 995415 - copy IMSI (%ws) to subscriberId",
            (char *)this + 13040);
          StringCchCopyW((unsigned __int16 *)this + 7124, 0x10u, (const unsigned __int16 *)this + 6520);
        }
        CWwanDataExecutorState::fsmEventHandler(this, 3);
      }
    }
    else
    {
      v17 = *(_DWORD *)a2;
      v14 = *((_DWORD *)this + 3186);
      v10 = *((_DWORD *)this + 3143);
      WwanLog::Error(
        "CWwanDataExecutorState::OnCanIMSIChange",
        0,
        L"(Modem {%s} EXEC %d): cImsi %d is not equal to number of configured lines (%d)",
        sz,
        v10,
        v14,
        v17);
    }
  }
  else
  {
    v13 = *(_DWORD *)a2;
    v9 = *((_DWORD *)this + 3143);
    WwanLog::Info(
      "CWwanDataExecutorState::OnCanIMSIChange",
      0,
      L"(Modem {%s} EXEC %d): IMSI change notification (cImsi %d) while can is deconfigured.",
      sz,
      v9,
      v13);
  }
}

```

## disassembly

```asm
0x18003cb2c  mov     [rsp+arg_10], rbx
0x18003cb31  push    rbp
0x18003cb32  push    rsi
0x18003cb33  push    rdi
0x18003cb34  sub     rsp, 0A0h
0x18003cb3b  mov     rax, cs:__security_cookie
0x18003cb42  xor     rax, rsp
0x18003cb45  mov     [rsp+0B8h+var_28], rax
0x18003cb4d  mov     rbx, rdx
0x18003cb50  mov     rdi, rcx
0x18003cb53  xor     edx, edx; Val
0x18003cb55  lea     rcx, [rsp+0B8h+sz]; void *
0x18003cb5a  lea     r8d, [rdx+4Ah]; Size
0x18003cb5e  call    memset_0
0x18003cb63  lea     rcx, [rdi+3108h]; rguid
0x18003cb6a  mov     r8d, 25h ; '%'; cchMax
0x18003cb70  lea     rdx, [rsp+0B8h+sz]; lpsz
0x18003cb75  call    cs:__imp_StringFromGUID2
0x18003cb7b  mov     ecx, [rdi+31C8h]
0x18003cb81  lea     r9, [rsp+0B8h+sz]
0x18003cb86  mov     eax, [rbx]
0x18003cb88  xor     ebp, ebp
0x18003cb8a  mov     edx, [rdi+311Ch]
0x18003cb90  test    ecx, ecx
0x18003cb92  jnz     short loc_18003CBB6
0x18003cb94  mov     [rsp+0B8h+var_90], eax
0x18003cb98  lea     r8, aModemSExecDIms_0; "(Modem {%s} EXEC %d): IMSI change notif"...
0x18003cb9f  mov     [rsp+0B8h+var_98], edx
0x18003cba3  lea     rcx, aCwwandataexecu_6; "CWwanDataExecutorState::OnCanIMSIChange"
0x18003cbaa  xor     edx, edx; struct _GUID *
0x18003cbac  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003cbb1  jmp     loc_18003CCFD
0x18003cbb6  cmp     ecx, eax
0x18003cbb8  jz      short loc_18003CBE0
0x18003cbba  mov     [rsp+0B8h+var_88], eax
0x18003cbbe  lea     r8, aModemSExecDCim; "(Modem {%s} EXEC %d): cImsi %d is not e"...
0x18003cbc5  mov     [rsp+0B8h+var_90], ecx
0x18003cbc9  lea     rcx, aCwwandataexecu_6; "CWwanDataExecutorState::OnCanIMSIChange"
0x18003cbd0  mov     [rsp+0B8h+var_98], edx
0x18003cbd4  xor     edx, edx; struct _GUID *
0x18003cbd6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18003cbdb  jmp     loc_18003CCFD
0x18003cbe0  cmp     [rdi+3920h], ebp
0x18003cbe6  jz      short loc_18003CC16
0x18003cbe8  lea     rax, [rdi+32F0h]
0x18003cbef  mov     qword ptr [rsp+0B8h+var_88], rax
0x18003cbf4  lea     r8, aModemSExecDIms; "(Modem {%s} EXEC %d): IMSI is notified "...
0x18003cbfb  mov     [rsp+0B8h+var_90], ecx
0x18003cbff  lea     rcx, aCwwandataexecu_6; "CWwanDataExecutorState::OnCanIMSIChange"
0x18003cc06  mov     [rsp+0B8h+var_98], edx
0x18003cc0a  xor     edx, edx; struct _GUID *
0x18003cc0c  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x18003cc11  jmp     loc_18003CCFD
0x18003cc16  mov     [rsp+0B8h+var_90], eax
0x18003cc1a  lea     r8, aModemSExecDIms_1; "(Modem {%s} EXEC %d): IMSI obtained (cI"...
0x18003cc21  mov     [rsp+0B8h+var_98], edx
0x18003cc25  lea     rcx, aCwwandataexecu_6; "CWwanDataExecutorState::OnCanIMSIChange"
0x18003cc2c  xor     edx, edx; struct _GUID *
0x18003cc2e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003cc33  movups  xmm0, xmmword ptr [rdi+32ECh]
0x18003cc3a  mov     eax, [rdi+332Ch]
0x18003cc40  lea     rsi, [rdi+37A8h]
0x18003cc47  movups  xmm1, xmmword ptr [rdi+32FCh]
0x18003cc4e  movups  xmmword ptr [rdi+3330h], xmm0
0x18003cc55  movups  xmm0, xmmword ptr [rdi+330Ch]
0x18003cc5c  movups  xmmword ptr [rdi+3340h], xmm1
0x18003cc63  movups  xmm1, xmmword ptr [rdi+331Ch]
0x18003cc6a  movups  xmmword ptr [rdi+3350h], xmm0
0x18003cc71  movups  xmmword ptr [rdi+3360h], xmm1
0x18003cc78  mov     [rdi+3370h], eax
0x18003cc7e  movaps  xmm0, xmmword ptr [rbx]
0x18003cc81  movups  xmmword ptr [rdi+32ECh], xmm0
0x18003cc88  movaps  xmm1, xmmword ptr [rbx+10h]
0x18003cc8c  movups  xmmword ptr [rdi+32FCh], xmm1
0x18003cc93  movaps  xmm0, xmmword ptr [rbx+20h]
0x18003cc97  movups  xmmword ptr [rdi+330Ch], xmm0
0x18003cc9e  movaps  xmm1, xmmword ptr [rbx+30h]
0x18003cca2  movups  xmmword ptr [rdi+331Ch], xmm1
0x18003cca9  mov     eax, [rbx+40h]
0x18003ccac  mov     [rdi+332Ch], eax
0x18003ccb2  mov     dword ptr [rdi+3920h], 1
0x18003ccbc  cmp     [rsi], bp
0x18003ccbf  jnz     short loc_18003CCF0
0x18003ccc1  lea     rbx, [rdi+32F0h]
0x18003ccc8  xor     edx, edx; struct _GUID *
0x18003ccca  mov     r9, rbx
0x18003cccd  lea     r8, aWorkAroundForB; "Work-around for bug 995415 - copy IMSI "...
0x18003ccd4  lea     rcx, aCwwandataexecu_6; "CWwanDataExecutorState::OnCanIMSIChange"
0x18003ccdb  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18003cce0  mov     r8, rbx; unsigned __int16 *
0x18003cce3  mov     edx, 10h; unsigned __int64
0x18003cce8  mov     rcx, rsi; unsigned __int16 *
0x18003cceb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ccf0  mov     edx, 3
0x18003ccf5  mov     rcx, rdi
0x18003ccf8  call    ?fsmEventHandler@CWwanDataExecutorState@@AEAAXW4_WwanDataExecutorStateFSMEvent@1@@Z; CWwanDataExecutorState::fsmEventHandler(CWwanDataExecutorState::_WwanDataExecutorStateFSMEvent)
0x18003ccfd  mov     rcx, [rsp+0B8h+var_28]
0x18003cd05  xor     rcx, rsp; StackCookie
0x18003cd08  call    __security_check_cookie
0x18003cd0d  mov     rbx, [rsp+0B8h+arg_10]
0x18003cd15  add     rsp, 0A0h
0x18003cd1c  pop     rdi
0x18003cd1d  pop     rsi
0x18003cd1e  pop     rbp
0x18003cd1f  retn
```
