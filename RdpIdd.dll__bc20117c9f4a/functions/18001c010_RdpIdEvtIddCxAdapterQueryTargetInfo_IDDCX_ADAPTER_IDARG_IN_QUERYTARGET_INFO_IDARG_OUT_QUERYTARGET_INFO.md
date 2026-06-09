# RdpIdEvtIddCxAdapterQueryTargetInfo(IDDCX_ADAPTER__ *,IDARG_IN_QUERYTARGET_INFO *,IDARG_OUT_QUERYTARGET_INFO *)

- ea: `0x18001c010`
- end: `0x18001c12d`
- name: `?RdpIdEvtIddCxAdapterQueryTargetInfo@@YAJPEAUIDDCX_ADAPTER__@@PEAUIDARG_IN_QUERYTARGET_INFO@@PEAUIDARG_OUT_QUERYTARGET_INFO@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(struct IDDCX_ADAPTER__ *, struct IDARG_IN_QUERYTARGET_INFO *, struct IDARG_OUT_QUERYTARGET_INFO *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000dbd8`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c06d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c0e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c06d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c0e6`

## pseudocode

```c
__int64 __fastcall RdpIdEvtIddCxAdapterQueryTargetInfo(
        struct IDDCX_ADAPTER__ *a1,
        struct IDARG_IN_QUERYTARGET_INFO *a2,
        struct IDARG_OUT_QUERYTARGET_INFO *a3)
{
  char v4; // bl
  bool v5; // si
  bool v6; // bp
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  bool v10; // di
  char v11; // al
  int v12; // r8d
  int v13; // edx
  int v15; // [rsp+20h] [rbp-68h]
  int v16; // [rsp+28h] [rbp-60h]

  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v15,
      v16,
      14,
      &WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids,
      CurrentThreadId);
  }
  *(_DWORD *)a3 = 3;
  *(_QWORD *)((char *)a3 + 4) = 6;
  *(_QWORD *)((char *)a3 + 12) = 0;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v4 = 0;
  }
  v10 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v11 = GetCurrentThreadId();
    LOBYTE(v12) = v10;
    LOBYTE(v13) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      v12,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v15,
      v16,
      15,
      &WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids,
      v11);
  }
  return 0;
}

```

## disassembly

```asm
0x18001c010  push    rbx
0x18001c012  push    rbp
0x18001c013  push    rsi
0x18001c014  push    rdi
0x18001c015  push    r12
0x18001c017  push    r13
0x18001c019  push    r15
0x18001c01b  sub     rsp, 50h
0x18001c01f  mov     rdi, r8
0x18001c022  mov     rax, cs:WPP_GLOBAL_Control
0x18001c029  lea     r12, WPP_GLOBAL_Control
0x18001c030  mov     bl, 1
0x18001c032  cmp     rax, r12
0x18001c035  jz      short loc_18001C047
0x18001c037  test    [rax+1Ch], bl
0x18001c03a  jz      short loc_18001C047
0x18001c03c  cmp     byte ptr [rax+19h], 4
0x18001c040  jb      short loc_18001C047
0x18001c042  mov     sil, bl
0x18001c045  jmp     short loc_18001C04A
0x18001c047  xor     sil, sil
0x18001c04a  lea     r15, WPP_RECORDER_INITIALIZED
0x18001c051  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c058  lea     r13, WPP_d8ec245d77ae37b19a0915f6501df12c_Traceguids
0x18001c05f  setnz   bpl
0x18001c063  test    sil, sil
0x18001c066  jnz     short loc_18001C06D
0x18001c068  test    bpl, bpl
0x18001c06b  jz      short loc_18001C0A3
0x18001c06d  call    cs:__imp_GetCurrentThreadId
0x18001c074  nop     dword ptr [rax+rax+00h]
0x18001c079  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c080  mov     r8b, bpl; int
0x18001c083  mov     dword ptr [rsp+88h+var_48], eax; char
0x18001c087  mov     dl, sil; int
0x18001c08a  mov     [rsp+88h+MessageGuid], r13; MessageGuid
0x18001c08f  mov     [rsp+88h+var_58], 0Eh; __int16
0x18001c096  mov     r9, [rcx+28h]; int
0x18001c09a  mov     rcx, [rcx+10h]; int
0x18001c09e  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001c0a3  mov     dword ptr [rdi], 3
0x18001c0a9  mov     qword ptr [rdi+4], 6
0x18001c0b1  mov     qword ptr [rdi+0Ch], 0
0x18001c0b9  mov     rax, cs:WPP_GLOBAL_Control
0x18001c0c0  cmp     rax, r12
0x18001c0c3  jz      short loc_18001C0D0
0x18001c0c5  test    [rax+1Ch], bl
0x18001c0c8  jz      short loc_18001C0D0
0x18001c0ca  cmp     byte ptr [rax+19h], 4
0x18001c0ce  jnb     short loc_18001C0D2
0x18001c0d0  xor     bl, bl
0x18001c0d2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c0d9  setnz   dil
0x18001c0dd  test    bl, bl
0x18001c0df  jnz     short loc_18001C0E6
0x18001c0e1  test    dil, dil
0x18001c0e4  jz      short loc_18001C11B
0x18001c0e6  call    cs:__imp_GetCurrentThreadId
0x18001c0ed  nop     dword ptr [rax+rax+00h]
0x18001c0f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0f9  mov     r8b, dil; int
0x18001c0fc  mov     dword ptr [rsp+88h+var_48], eax; char
0x18001c100  mov     dl, bl; int
0x18001c102  mov     [rsp+88h+MessageGuid], r13; MessageGuid
0x18001c107  mov     [rsp+88h+var_58], 0Fh; __int16
0x18001c10e  mov     r9, [rcx+28h]; int
0x18001c112  mov     rcx, [rcx+10h]; int
0x18001c116  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001c11b  xor     eax, eax
0x18001c11d  add     rsp, 50h
0x18001c121  pop     r15
0x18001c123  pop     r13
0x18001c125  pop     r12
0x18001c127  pop     rdi
0x18001c128  pop     rsi
0x18001c129  pop     rbp
0x18001c12a  pop     rbx
0x18001c12b  retn
```
