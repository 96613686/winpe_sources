# WfpStringCopy

- ea: `0x180012e20`
- end: `0x180013106`
- name: `WfpStringCopy`
- size: `742`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `12`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180010480`
- `0x180023c88`
- `0x180023f18`
- `0x180029174`
- `0x180032a2c`
- `0x18003489c`
- `0x180045da4`
- `0x18004a59c`
- `0x18004c680`
- `0x18004cce8`
- `0x180068a30`
- `0x180072f20`

## callees

- `0x18000fb34`
- `0x180011510`
- `0x180012e20`
- `0x1800135ac`
- `0x1800197d0`
- `0x18004fb50`
- `0x1800560f8`
- `0x18005aa60`
- `0x18008ad6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012eb3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012eb3`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800130ee`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800130ee`

## string_xrefs

- `0x180012fad`: `WfpBufferCopy`
- `0x180013090`: `WfpStringCopy`

## pseudocode

```c
__int64 __fastcall WfpStringCopy(_WORD *Src, __int64 a2, void **a3)
{
  __int64 result; // rax
  __int64 v6; // rax
  SIZE_T v8; // rbp
  __int64 v9; // rsi
  void *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdi
  _QWORD *v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rax
  int v17; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v18[16]; // [rsp+38h] [rbp-60h] BYREF
  const char *v19; // [rsp+48h] [rbp-50h]
  __int64 v20; // [rsp+50h] [rbp-48h]
  int *v21; // [rsp+58h] [rbp-40h]
  __int64 v22; // [rsp+60h] [rbp-38h]

  *a3 = 0;
  result = 0;
  if ( Src )
  {
    v6 = -1;
    while ( Src[++v6] != 0 )
      ;
    v8 = 2 * v6 + 2;
    v9 = 0;
    if ( 2 * v6 == -2 )
      goto LABEL_24;
    if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(Src, a2, a3) )
    {
      v13 = WfpMemAlloc25B(v8);
    }
    else
    {
      v10 = HeapAlloc(gWfpHeap, 0, v8);
      *a3 = v10;
      if ( v10 )
      {
        v13 = 0;
        if ( gWfpTrackHeapBytes )
          _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v10));
      }
      else
      {
        v16 = WfpReportSysErrorAsNtStatus(v11, "HeapAlloc", 3221225495LL);
        v13 = v16;
        if ( v16 )
          WfpReportError(v16, "WfpMemAlloc");
      }
    }
    if ( v13 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v12, 0, (__int64)"WfpPoolAllocNonPaged", v13);
        v14 = WPP_GLOBAL_Control;
      }
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
      {
        v17 = v13;
        v21 = &v17;
        v19 = "WfpPoolAllocNonPaged";
        v20 = 21;
        v22 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          &MICROSOFT_WFP_PROVIDER_Context,
          (__int64)WFP_USERMODE_ERROR,
          v12,
          3,
          (__int64)v18);
        v14 = WPP_GLOBAL_Control;
        goto LABEL_19;
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
    }
    if ( !v13 )
    {
      memcpy_0(*a3, Src, v8);
      return 0;
    }
LABEL_19:
    v9 = v13;
    v15 = v13;
    if ( v14 != &WPP_GLOBAL_Control && *((_BYTE *)v14 + 25) >= 2u && (*((_BYTE *)v14 + 28) & 1) != 0 )
      WPP_SF_Ssd(v14[2], 26, v12, 0, (__int64)"WfpBufferCopy", v13);
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v17 = v13;
      v21 = &v17;
      v19 = "WfpBufferCopy";
      v20 = 14;
      v22 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        &MICROSOFT_WFP_PROVIDER_Context,
        (__int64)WFP_USERMODE_ERROR,
        v12,
        3,
        (__int64)v18);
      goto LABEL_30;
    }
LABEL_24:
    v15 = v9;
    if ( !v9 )
      return v15;
LABEL_30:
    WfpReportError(v9, "WfpStringCopy");
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x180012e20  mov     r11, rsp
0x180012e23  push    rbx
0x180012e24  push    r14
0x180012e26  push    r15
0x180012e28  sub     rsp, 80h
0x180012e2f  mov     rax, cs:__security_cookie
0x180012e36  xor     rax, rsp
0x180012e39  mov     [rsp+98h+var_30], rax
0x180012e3e  xor     r15d, r15d
0x180012e41  mov     r14, r8
0x180012e44  mov     [r8], r15
0x180012e47  mov     rbx, rcx
0x180012e4a  mov     eax, r15d
0x180012e4d  test    rcx, rcx
0x180012e50  jz      loc_180013011
0x180012e56  mov     [r11+10h], rbp
0x180012e5a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180012e61  mov     [r11+20h], rsi
0x180012e65  nop     word ptr [rax+rax+00000000h]
0x180012e70  cmp     [rcx+rax*2+2], r15w
0x180012e76  lea     rax, [rax+1]
0x180012e7a  jnz     short loc_180012E70
0x180012e7c  lea     rbp, ds:2[rax*2]
0x180012e84  mov     [rsp+98h+var_20], rdi
0x180012e89  mov     [rsp+98h+var_28], r12
0x180012e8e  mov     rsi, r15
0x180012e91  test    rbp, rbp
0x180012e94  jz      loc_180012FE8
0x180012e9a  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180012e9f  xor     edx, edx; dwFlags
0x180012ea1  test    eax, eax
0x180012ea3  jnz     loc_18001302C
0x180012ea9  mov     rcx, cs:gWfpHeap; hHeap
0x180012eb0  mov     r8, rbp; dwBytes
0x180012eb3  call    cs:__imp_HeapAlloc
0x180012eba  nop     dword ptr [rax+rax+00h]
0x180012ebf  mov     [r14], rax
0x180012ec2  test    rax, rax
0x180012ec5  jz      loc_1800130B0
0x180012ecb  cmp     cs:gWfpTrackHeapBytes, r15d
0x180012ed2  mov     rdi, r15
0x180012ed5  jnz     loc_1800130E2
0x180012edb  lea     r12, WPP_GLOBAL_Control
0x180012ee2  test    rdi, rdi
0x180012ee5  jz      loc_1800130A4
0x180012eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ef2  lea     rsi, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x180012ef9  cmp     rcx, r12
0x180012efc  jz      short loc_180012F2B
0x180012efe  cmp     byte ptr [rcx+19h], 2
0x180012f02  jb      short loc_180012F2B
0x180012f04  test    byte ptr [rcx+1Ch], 1
0x180012f08  jz      short loc_180012F2B
0x180012f0a  mov     rcx, [rcx+10h]
0x180012f0e  mov     edx, 1Ah
0x180012f13  mov     [rsp+98h+var_70], edi
0x180012f17  xor     r9d, r9d
0x180012f1a  mov     [rsp+98h+var_78], rsi
0x180012f1f  call    WPP_SF_Ssd
0x180012f24  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f2b  cmp     cs:gWfpLogUserModeErrors, r15d
0x180012f32  jnz     short loc_180012F4F
0x180012f34  test    rdi, rdi
0x180012f37  jnz     short loc_180012FA7
0x180012f39  mov     rcx, [r14]; void *
0x180012f3c  mov     r8, rbp; Size
0x180012f3f  mov     rdx, rbx; Src
0x180012f42  call    memcpy_0
0x180012f47  mov     rax, rdi
0x180012f4a  jmp     loc_180012FF7
0x180012f4f  test    cs:byte_1800F6115, 1
0x180012f56  jz      short loc_180012F34
0x180012f58  lea     rax, [rsp+98h+var_68]
0x180012f5d  mov     [rsp+98h+var_68], edi
0x180012f61  mov     [rsp+98h+var_40], rax
0x180012f66  lea     rdx, WFP_USERMODE_ERROR
0x180012f6d  lea     rax, [rsp+98h+var_60]
0x180012f72  mov     [rsp+98h+var_50], rsi
0x180012f77  mov     r9d, 3
0x180012f7d  mov     [rsp+98h+var_78], rax
0x180012f82  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180012f89  mov     [rsp+98h+var_48], 15h
0x180012f92  mov     [rsp+98h+var_38], 4
0x180012f9b  call    McGenEventWrite_EtwEventWriteTransfer
0x180012fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180012fa7  mov     rsi, rdi
0x180012faa  mov     rbx, rdi
0x180012fad  lea     rbp, aWfpbuffercopy; "WfpBufferCopy"
0x180012fb4  cmp     rcx, r12
0x180012fb7  jz      short loc_180012FDF
0x180012fb9  cmp     byte ptr [rcx+19h], 2
0x180012fbd  jb      short loc_180012FDF
0x180012fbf  test    byte ptr [rcx+1Ch], 1
0x180012fc3  jz      short loc_180012FDF
0x180012fc5  mov     rcx, [rcx+10h]
0x180012fc9  mov     edx, 1Ah
0x180012fce  mov     [rsp+98h+var_70], edi
0x180012fd2  xor     r9d, r9d
0x180012fd5  mov     [rsp+98h+var_78], rbp
0x180012fda  call    WPP_SF_Ssd
0x180012fdf  cmp     cs:gWfpLogUserModeErrors, r15d
0x180012fe6  jnz     short loc_18001303F
0x180012fe8  mov     rbx, rsi
0x180012feb  test    rsi, rsi
0x180012fee  jnz     loc_180013090
0x180012ff4  mov     rax, rbx
0x180012ff7  mov     rdi, [rsp+98h+var_20]
0x180012ffc  mov     r12, [rsp+98h+var_28]
0x180013001  mov     rbp, [rsp+98h+arg_8]
0x180013009  mov     rsi, [rsp+98h+arg_18]
0x180013011  mov     rcx, [rsp+98h+var_30]
0x180013016  xor     rcx, rsp; StackCookie
0x180013019  call    __security_check_cookie
0x18001301e  add     rsp, 80h
0x180013025  pop     r15
0x180013027  pop     r14
0x180013029  pop     rbx
0x18001302a  retn
0x18001302c  mov     r8, r14
0x18001302f  mov     rcx, rbp; dwBytes
0x180013032  call    WfpMemAlloc25B
0x180013037  mov     rdi, rax
0x18001303a  jmp     loc_180012EDB
0x18001303f  test    cs:byte_1800F6115, 1
0x180013046  jz      short loc_180012FE8
0x180013048  lea     rax, [rsp+98h+var_68]
0x18001304d  mov     [rsp+98h+var_68], edi
0x180013051  mov     [rsp+98h+var_40], rax
0x180013056  lea     rdx, WFP_USERMODE_ERROR
0x18001305d  lea     rax, [rsp+98h+var_60]
0x180013062  mov     [rsp+98h+var_50], rbp
0x180013067  mov     r9d, 3
0x18001306d  mov     [rsp+98h+var_78], rax
0x180013072  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180013079  mov     [rsp+98h+var_48], 0Eh
0x180013082  mov     [rsp+98h+var_38], 4
0x18001308b  call    McGenEventWrite_EtwEventWriteTransfer
0x180013090  lea     rdx, aWfpstringcopy; "WfpStringCopy"
0x180013097  mov     rcx, rsi
0x18001309a  call    WfpReportError
0x18001309f  jmp     loc_180012FF4
0x1800130a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800130ab  jmp     loc_180012F34
0x1800130b0  mov     r8d, 0C0000017h
0x1800130b6  lea     rdx, aHeapalloc; "HeapAlloc"
0x1800130bd  call    WfpReportSysErrorAsNtStatus
0x1800130c2  mov     rdi, rax
0x1800130c5  test    rax, rax
0x1800130c8  jz      loc_180012EDB
0x1800130ce  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x1800130d5  mov     rcx, rax
0x1800130d8  call    WfpReportError
0x1800130dd  jmp     loc_180012EDB
0x1800130e2  mov     rcx, cs:gWfpHeap; hHeap
0x1800130e9  mov     r8, rax; lpMem
0x1800130ec  xor     edx, edx; dwFlags
0x1800130ee  call    cs:__imp_HeapSize
0x1800130f5  nop     dword ptr [rax+rax+00h]
0x1800130fa  lock add cs:gWfpHeapBytesAllocated, eax
0x180013101  jmp     loc_180012EDB
```
