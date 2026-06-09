# VEMgrNotifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::SendNotification(ulong,ulong,ulong,wchar_t const *,wchar_t const *,ulong,ulong,bool)

- ea: `0x180009434`
- end: `0x18000970a`
- name: `?SendNotification@?$VEMgrNotifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJKKKPEB_W0KK_N@Z`
- size: `726`
- prototype: `__int64 __fastcall(int, int, int, _WORD *, void *Src, int, int, char)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800021d0`
- `0x18000d850`
- `0x18000fbf4`
- `0x180018484`

## callees

- `0x180009434`
- `0x18000e8d4`
- `0x18000fdc0`
- `0x18001bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800096c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800096e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800096c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800096e0`
- `ntoskrnl!KeDelayExecutionThread` at `0x180009605`
- `ntoskrnl!KeDelayExecutionThread` at `0x180009605`
- `FLTMGR!FltSendMessage` at `0x1800095c5`
- `FLTMGR!FltSendMessage` at `0x180009662`
- `FLTMGR!FltSendMessage` at `0x1800095c5`
- `FLTMGR!FltSendMessage` at `0x180009662`

## pseudocode

```c
__int64 __fastcall VEMgrNotifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::SendNotification(
        int a1,
        int a2,
        int a3,
        _WORD *a4,
        void *Src,
        int a6,
        int a7,
        char a8)
{
  __int64 v8; // rax
  __int64 v12; // rbx
  void *v13; // r15
  unsigned __int16 v14; // bx
  size_t v15; // r14
  unsigned int v16; // edx
  int v17; // eax
  _DWORD *v18; // rdi
  int v19; // eax
  char *v20; // rbx
  int v21; // esi
  int v22; // ebx
  __int64 v23; // rcx
  unsigned int v24; // ebx
  PFLT_PORT *v25; // rdx
  struct _FLT_FILTER *v26; // rcx
  int v27; // esi
  __int64 v28; // rcx
  PFLT_PORT *v29; // rdx
  struct _FLT_FILTER *v30; // rcx
  NTSTATUS v31; // eax
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp-20h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+48h] [rbp-18h] BYREF
  ULONG SenderBufferLength[2]; // [rsp+50h] [rbp-10h] BYREF
  PVOID SenderBuffer; // [rsp+58h] [rbp-8h]
  int ReplyBuffer; // [rsp+B8h] [rbp+58h] BYREF

  v8 = -1;
  *(_QWORD *)SenderBufferLength = 0;
  SenderBuffer = 0;
  if ( a4 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a4[v12] );
  }
  else
  {
    LOWORD(v12) = 0;
  }
  v13 = Src;
  v14 = 2 * v12;
  if ( Src )
  {
    do
      ++v8;
    while ( *((_WORD *)Src + v8) );
  }
  else
  {
    LOWORD(v8) = 0;
  }
  v15 = (unsigned __int16)(2 * v8);
  v16 = v15 + v14 + 36;
  if ( v16 > 0x4B6 )
    return 3221225626LL;
  v17 = appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
          SenderBufferLength,
          v16);
  v18 = SenderBuffer;
  if ( v17 < 0 )
  {
    if ( SenderBuffer )
      ExFreePoolWithTag(SenderBuffer, 0);
    return 3221225626LL;
  }
  if ( !SenderBuffer )
    return 3221225626LL;
  *(_DWORD *)SenderBuffer = a1;
  v18[3] = a7;
  v19 = a6;
  v18[2] = a3;
  v18[4] = v19;
  v18[1] = a2;
  *((_WORD *)v18 + 12) = v14;
  *((_WORD *)v18 + 16) = v15;
  if ( a4 && v14 )
  {
    memmove(v18 + 9, a4, v14);
    v20 = (char *)v18 + v14 + 36;
    v21 = 36;
  }
  else
  {
    v20 = (char *)(v18 + 9);
    v21 = 0;
  }
  v18[5] = v21;
  if ( v13 && (_WORD)v15 )
  {
    memmove(v20, v13, v15);
    v22 = (_DWORD)v20 - (_DWORD)v18;
  }
  else
  {
    v22 = 0;
  }
  v18[7] = v22;
  Timeout.QuadPart = -18000000000LL;
  ReplyBuffer = 0;
  LODWORD(Src) = 4;
  v23 = *((_QWORD *)g_VeMgrFltData + 1);
  if ( *(_BYTE *)(v23 + 32) )
  {
    v24 = -1073741595;
  }
  else
  {
    v25 = (PFLT_PORT *)(v23 + 8);
    if ( *(_QWORD *)(v23 + 8) && (v26 = *(struct _FLT_FILTER **)(v23 + 40)) != 0 )
    {
      v24 = FltSendMessage(v26, v25, v18, SenderBufferLength[0], &ReplyBuffer, (PULONG)&Src, &Timeout);
      if ( v24 == 258 )
        v24 = -1073741595;
    }
    else
    {
      v24 = -1073741661;
    }
  }
  if ( !a8 )
  {
LABEL_39:
    if ( v24 == -1073741661 && (byte_180027405 & 4) != 0 )
      McTemplateK0z_EtwWriteTransfer(
        PROVIDER_MICROSOFT_APPV_CLIENT_Context,
        APPV_CLIENT_Evt_AppLaunchFailedServiceNotRunning,
        &GUID_NULL,
        a4);
    goto LABEL_42;
  }
  if ( v24 == -1073741661 )
  {
    v27 = 0;
    Interval.QuadPart = -300000000;
    while ( 1 )
    {
      KeDelayExecutionThread(0, 0, &Interval);
      LODWORD(Src) = 4;
      v28 = *((_QWORD *)g_VeMgrFltData + 1);
      if ( *(_BYTE *)(v28 + 32) )
        break;
      v29 = (PFLT_PORT *)(v28 + 8);
      if ( *(_QWORD *)(v28 + 8) && (v30 = *(struct _FLT_FILTER **)(v28 + 40)) != 0 )
      {
        v31 = FltSendMessage(v30, v29, v18, SenderBufferLength[0], &ReplyBuffer, (PULONG)&Src, &Timeout);
        v24 = v31;
        if ( v31 == 258 )
        {
          v24 = -1073741595;
          goto LABEL_42;
        }
        if ( v31 != -1073741661 )
          goto LABEL_42;
      }
      else
      {
        v24 = -1073741661;
      }
      if ( (unsigned int)++v27 >= 0xA )
        goto LABEL_39;
    }
    v24 = -1073741595;
    goto LABEL_39;
  }
LABEL_42:
  if ( v18 )
    ExFreePoolWithTag(v18, 0);
  return v24;
}

```

## disassembly

```asm
0x180009434  mov     [rsp-38h+arg_8], rbx
0x180009439  mov     [rsp-38h+arg_0], ecx
0x18000943d  push    rbp
0x18000943e  push    rsi
0x18000943f  push    rdi
0x180009440  push    r12
0x180009442  push    r13
0x180009444  push    r14
0x180009446  push    r15
0x180009448  mov     rbp, rsp
0x18000944b  sub     rsp, 60h
0x18000944f  xor     ecx, ecx
0x180009451  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009455  mov     qword ptr [rbp+SenderBufferLength], rcx
0x180009459  mov     r13, r9
0x18000945c  mov     [rbp+SenderBuffer], rcx
0x180009460  mov     esi, r8d
0x180009463  mov     r12d, edx
0x180009466  test    r9, r9
0x180009469  jnz     short loc_18000946F
0x18000946b  mov     ebx, ecx
0x18000946d  jmp     short loc_18000947C
0x18000946f  mov     rbx, rax
0x180009472  inc     rbx
0x180009475  cmp     [r9+rbx*2], cx
0x18000947a  jnz     short loc_180009472
0x18000947c  mov     r15, [rbp+Src]
0x180009480  add     bx, bx
0x180009483  test    r15, r15
0x180009486  jnz     short loc_18000948D
0x180009488  mov     rax, rcx
0x18000948b  jmp     short loc_180009497
0x18000948d  inc     rax
0x180009490  cmp     [r15+rax*2], cx
0x180009495  jnz     short loc_18000948D
0x180009497  add     ax, ax
0x18000949a  movzx   edx, bx
0x18000949d  add     edx, 24h ; '$'
0x1800094a0  movzx   r14d, ax
0x1800094a4  add     edx, r14d
0x1800094a7  cmp     edx, 4B6h
0x1800094ad  ja      loc_1800096EC
0x1800094b3  lea     rcx, [rbp+SenderBufferLength]
0x1800094b7  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x1800094bc  mov     rdi, [rbp+SenderBuffer]
0x1800094c0  xor     r8d, r8d
0x1800094c3  test    eax, eax
0x1800094c5  js      loc_1800096D6
0x1800094cb  test    rdi, rdi
0x1800094ce  jz      loc_1800096EC
0x1800094d4  mov     eax, [rbp+arg_0]
0x1800094d7  mov     [rdi], eax
0x1800094d9  mov     eax, [rbp+arg_30]
0x1800094dc  mov     [rdi+0Ch], eax
0x1800094df  mov     eax, [rbp+arg_28]
0x1800094e2  mov     [rdi+8], esi
0x1800094e5  lea     rsi, [rdi+24h]
0x1800094e9  mov     [rdi+10h], eax
0x1800094ec  mov     [rdi+4], r12d
0x1800094f0  mov     [rdi+18h], bx
0x1800094f4  mov     [rdi+20h], r14w
0x1800094f9  test    r13, r13
0x1800094fc  jz      short loc_18000951E
0x1800094fe  test    bx, bx
0x180009501  jz      short loc_18000951E
0x180009503  movzx   ebx, bx
0x180009506  mov     rdx, r13; Src
0x180009509  mov     r8d, ebx; Size
0x18000950c  mov     rcx, rsi; void *
0x18000950f  call    memmove
0x180009514  add     rbx, rsi
0x180009517  sub     esi, edi
0x180009519  xor     r8d, r8d
0x18000951c  jmp     short loc_180009524
0x18000951e  mov     rbx, rsi
0x180009521  mov     esi, r8d
0x180009524  mov     [rdi+14h], esi
0x180009527  mov     r12d, edi
0x18000952a  test    r15, r15
0x18000952d  jz      short loc_18000954A
0x18000952f  test    r14w, r14w
0x180009533  jz      short loc_18000954A
0x180009535  mov     r8, r14; Size
0x180009538  mov     rdx, r15; Src
0x18000953b  mov     rcx, rbx; void *
0x18000953e  call    memmove
0x180009543  sub     ebx, edi
0x180009545  xor     r8d, r8d
0x180009548  jmp     short loc_18000954D
0x18000954a  mov     ebx, r8d
0x18000954d  mov     [rdi+1Ch], ebx
0x180009550  mov     rax, 0FFFFFFFBCF1DCC00h
0x18000955a  mov     qword ptr [rbp+var_20], rax
0x18000955e  mov     r12d, 4
0x180009564  mov     rax, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x18000956b  mov     r14d, 0C00000A3h
0x180009571  mov     [rbp+arg_18], r8d
0x180009575  mov     dword ptr [rbp+Src], r12d
0x180009579  mov     rcx, [rax+8]
0x18000957d  lea     r15d, [r14+42h]
0x180009581  cmp     [rcx+20h], r8b
0x180009585  jz      short loc_18000958C
0x180009587  mov     ebx, r15d
0x18000958a  jmp     short loc_1800095DF
0x18000958c  lea     rdx, [rcx+8]; ClientPort
0x180009590  cmp     [rdx], r8
0x180009593  jnz     short loc_18000959A
0x180009595  mov     ebx, r14d
0x180009598  jmp     short loc_1800095DF
0x18000959a  mov     rcx, [rcx+28h]; Filter
0x18000959e  test    rcx, rcx
0x1800095a1  jz      short loc_180009595
0x1800095a3  mov     r9d, [rbp+SenderBufferLength]; SenderBufferLength
0x1800095a7  lea     rax, [rbp+var_20]
0x1800095ab  mov     [rsp+60h+Timeout], rax; Timeout
0x1800095b0  mov     r8, rdi; SenderBuffer
0x1800095b3  lea     rax, [rbp+Src]
0x1800095b7  mov     [rsp+60h+ReplyLength], rax; ReplyLength
0x1800095bc  lea     rax, [rbp+arg_18]
0x1800095c0  mov     [rsp+60h+ReplyBuffer], rax; ReplyBuffer
0x1800095c5  call    cs:__imp_FltSendMessage
0x1800095cc  nop     dword ptr [rax+rax+00h]
0x1800095d1  cmp     eax, 102h
0x1800095d6  mov     ebx, eax
0x1800095d8  cmovz   ebx, r15d
0x1800095dc  xor     r8d, r8d
0x1800095df  cmp     [rbp+arg_38], r8b
0x1800095e3  jz      loc_180009691
0x1800095e9  cmp     ebx, r14d
0x1800095ec  jnz     loc_1800096BC
0x1800095f2  mov     esi, r8d
0x1800095f5  mov     qword ptr [rbp+Interval], 0FFFFFFFFEE1E5D00h
0x1800095fd  lea     r8, [rbp+Interval]; Interval
0x180009601  xor     edx, edx; Alertable
0x180009603  xor     ecx, ecx; WaitMode
0x180009605  call    cs:__imp_KeDelayExecutionThread
0x18000960c  nop     dword ptr [rax+rax+00h]
0x180009611  mov     rax, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x180009618  xor     r8d, r8d
0x18000961b  mov     dword ptr [rbp+Src], r12d
0x18000961f  mov     rcx, [rax+8]
0x180009623  cmp     [rcx+20h], r8b
0x180009627  jnz     short loc_18000968E
0x180009629  lea     rdx, [rcx+8]; ClientPort
0x18000962d  cmp     [rdx], r8
0x180009630  jnz     short loc_180009637
0x180009632  mov     ebx, r14d
0x180009635  jmp     short loc_18000967C
0x180009637  mov     rcx, [rcx+28h]; Filter
0x18000963b  test    rcx, rcx
0x18000963e  jz      short loc_180009632
0x180009640  mov     r9d, [rbp+SenderBufferLength]; SenderBufferLength
0x180009644  lea     rax, [rbp+var_20]
0x180009648  mov     [rsp+60h+Timeout], rax; Timeout
0x18000964d  mov     r8, rdi; SenderBuffer
0x180009650  lea     rax, [rbp+Src]
0x180009654  mov     [rsp+60h+ReplyLength], rax; ReplyLength
0x180009659  lea     rax, [rbp+arg_18]
0x18000965d  mov     [rsp+60h+ReplyBuffer], rax; ReplyBuffer
0x180009662  call    cs:__imp_FltSendMessage
0x180009669  nop     dword ptr [rax+rax+00h]
0x18000966e  mov     ebx, eax
0x180009670  cmp     eax, 102h
0x180009675  jz      short loc_180009689
0x180009677  cmp     eax, r14d
0x18000967a  jnz     short loc_1800096BC
0x18000967c  inc     esi
0x18000967e  cmp     esi, 0Ah
0x180009681  jb      loc_1800095FD
0x180009687  jmp     short loc_180009691
0x180009689  mov     ebx, r15d
0x18000968c  jmp     short loc_1800096BC
0x18000968e  mov     ebx, r15d
0x180009691  cmp     ebx, r14d
0x180009694  jnz     short loc_1800096BC
0x180009696  test    cs:byte_180027405, r12b
0x18000969d  jz      short loc_1800096BC
0x18000969f  mov     r9, r13
0x1800096a2  lea     r8, GUID_NULL
0x1800096a9  lea     rdx, APPV_CLIENT_Evt_AppLaunchFailedServiceNotRunning
0x1800096b0  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x1800096b7  call    McTemplateK0z_EtwWriteTransfer
0x1800096bc  test    rdi, rdi
0x1800096bf  jz      short loc_1800096D2
0x1800096c1  xor     edx, edx; Tag
0x1800096c3  mov     rcx, rdi; P
0x1800096c6  call    cs:__imp_ExFreePoolWithTag
0x1800096cd  nop     dword ptr [rax+rax+00h]
0x1800096d2  mov     eax, ebx
0x1800096d4  jmp     short loc_1800096F1
0x1800096d6  test    rdi, rdi
0x1800096d9  jz      short loc_1800096EC
0x1800096db  xor     edx, edx; Tag
0x1800096dd  mov     rcx, rdi; P
0x1800096e0  call    cs:__imp_ExFreePoolWithTag
0x1800096e7  nop     dword ptr [rax+rax+00h]
0x1800096ec  mov     eax, 0C000009Ah
0x1800096f1  mov     rbx, [rsp+60h+arg_8]
0x1800096f9  add     rsp, 60h
0x1800096fd  pop     r15
0x1800096ff  pop     r14
0x180009701  pop     r13
0x180009703  pop     r12
0x180009705  pop     rdi
0x180009706  pop     rsi
0x180009707  pop     rbp
0x180009708  retn
```
