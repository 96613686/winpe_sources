# MpCmdUtils::DeleteReparsePoint

- ea: `0x14002476c`
- end: `0x140024982`
- name: `MpCmdUtils::DeleteReparsePoint`
- size: `534`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140024984`

## callees

- `0x14000493c`
- `0x140005c20`
- `0x140005c40`
- `0x14001da70`
- `0x140021e54`
- `0x14002476c`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1400247f8`
- `KERNEL32!DeviceIoControl` at `0x1400248d0`
- `KERNEL32!DeviceIoControl` at `0x1400247f8`
- `KERNEL32!DeviceIoControl` at `0x1400248d0`

## pseudocode

```c
__int64 __fastcall MpCmdUtils::DeleteReparsePoint(HANDLE hDevice)
{
  DWORD nOutBufferSize; // edi
  unsigned int v3; // esi
  _WORD *v4; // rbx
  unsigned int LastFailure; // eax
  void *v7; // rcx
  unsigned int v8; // edi
  LPVOID lpInBuffer; // [rsp+40h] [rbp-38h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-30h] BYREF

  BytesReturned = 0;
  lpInBuffer = 0;
  nOutBufferSize = 512;
  while ( 1 )
  {
    v3 = CommonUtil::MpNewBuffer<unsigned char>(&lpInBuffer, nOutBufferSize);
    if ( (v3 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids, v3);
      v7 = lpInBuffer;
      if ( lpInBuffer )
LABEL_27:
        operator delete(v7);
      return v3;
    }
    v4 = lpInBuffer;
    if ( DeviceIoControl(hDevice, 0x900A8u, 0, 0, lpInBuffer, nOutBufferSize, &BytesReturned, 0) )
      break;
    LastFailure = HrGetLastFailure();
    v3 = LastFailure;
    if ( LastFailure != -2147024774 && LastFailure != -2147024662 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids, LastFailure);
      if ( v4 )
      {
LABEL_16:
        v7 = v4;
        goto LABEL_27;
      }
      return v3;
    }
    nOutBufferSize *= 2;
    if ( v4 )
    {
      operator delete(v4);
      v4 = 0;
      lpInBuffer = 0;
    }
    if ( nOutBufferSize >= 0x4000 )
      goto LABEL_9;
  }
  if ( nOutBufferSize < 0x18 )
  {
LABEL_9:
    if ( v4 )
      operator delete(v4);
    return 2147943759LL;
  }
  else
  {
    BytesReturned = 0;
    v4[2] = 0;
    if ( DeviceIoControl(hDevice, 0x900ACu, v4, 0x18u, 0, 0, &BytesReturned, 0) )
      goto LABEL_16;
    v8 = HrGetLastFailure();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids, v8);
    operator delete(v4);
    return v8;
  }
}

```

## disassembly

```asm
0x14002476c  mov     [rsp+arg_8], rbx
0x140024771  mov     [rsp+arg_10], rbp
0x140024776  push    rsi
0x140024777  push    rdi
0x140024778  push    r14
0x14002477a  sub     rsp, 60h
0x14002477e  mov     rax, cs:__security_cookie
0x140024785  xor     rax, rsp
0x140024788  mov     [rsp+78h+var_28], rax
0x14002478d  xor     r14d, r14d
0x140024790  mov     rbp, rcx
0x140024793  mov     ebx, r14d
0x140024796  mov     [rsp+78h+BytesReturned], r14d
0x14002479b  mov     [rsp+78h+lpInBuffer], rbx
0x1400247a0  mov     edi, 200h
0x1400247a5  test    rbx, rbx
0x1400247a8  jz      short loc_1400247B7
0x1400247aa  mov     rcx, rbx; void *
0x1400247ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400247b2  mov     [rsp+78h+lpInBuffer], r14
0x1400247b7  mov     edx, edi
0x1400247b9  lea     rcx, [rsp+78h+lpInBuffer]
0x1400247be  call    ??$MpNewBuffer@E@CommonUtil@@YAJPEAPEAE_K@Z; CommonUtil::MpNewBuffer<uchar>(uchar * *,unsigned __int64)
0x1400247c3  mov     esi, eax
0x1400247c5  test    eax, eax
0x1400247c7  js      loc_14002491E
0x1400247cd  mov     rbx, [rsp+78h+lpInBuffer]
0x1400247d2  lea     rax, [rsp+78h+BytesReturned]
0x1400247d7  mov     [rsp+78h+lpOverlapped], r14; lpOverlapped
0x1400247dc  xor     r9d, r9d; nInBufferSize
0x1400247df  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x1400247e4  xor     r8d, r8d; lpInBuffer
0x1400247e7  mov     [rsp+78h+nOutBufferSize], edi; nOutBufferSize
0x1400247eb  mov     edx, 900A8h; dwIoControlCode
0x1400247f0  mov     rcx, rbp; hDevice
0x1400247f3  mov     [rsp+78h+lpOutBuffer], rbx; lpOutBuffer
0x1400247f8  call    cs:__imp_DeviceIoControl
0x1400247fe  test    eax, eax
0x140024800  jnz     loc_140024897
0x140024806  call    HrGetLastFailure
0x14002480b  mov     esi, eax
0x14002480d  cmp     eax, 8007007Ah
0x140024812  jz      short loc_14002481B
0x140024814  cmp     eax, 800700EAh
0x140024819  jnz     short loc_140024855
0x14002481b  add     edi, edi
0x14002481d  test    rbx, rbx
0x140024820  jz      short loc_140024832
0x140024822  mov     rcx, rbx; void *
0x140024825  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002482a  mov     rbx, r14
0x14002482d  mov     [rsp+78h+lpInBuffer], rbx
0x140024832  cmp     edi, 4000h
0x140024838  jb      loc_1400247A5
0x14002483e  test    rbx, rbx
0x140024841  jz      short loc_14002484B
0x140024843  mov     rcx, rbx; void *
0x140024846  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002484b  mov     eax, 8007054Fh
0x140024850  jmp     loc_140024960
0x140024855  mov     rcx, cs:WPP_GLOBAL_Control
0x14002485c  lea     rax, WPP_GLOBAL_Control
0x140024863  cmp     rcx, rax
0x140024866  jz      short loc_140024886
0x140024868  test    byte ptr [rcx+1Ch], 1
0x14002486c  jz      short loc_140024886
0x14002486e  mov     rcx, [rcx+10h]
0x140024872  lea     r8, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids
0x140024879  mov     edx, 20h ; ' '
0x14002487e  mov     r9d, esi
0x140024881  call    WPP_SF_d
0x140024886  test    rbx, rbx
0x140024889  jz      loc_14002495E
0x14002488f  mov     rcx, rbx
0x140024892  jmp     loc_140024959
0x140024897  mov     r9d, 18h; nInBufferSize
0x14002489d  cmp     edi, r9d
0x1400248a0  jb      short loc_14002483E
0x1400248a2  mov     [rsp+78h+lpOverlapped], r14; lpOverlapped
0x1400248a7  lea     rax, [rsp+78h+BytesReturned]
0x1400248ac  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x1400248b1  mov     r8, rbx; lpInBuffer
0x1400248b4  mov     [rsp+78h+BytesReturned], r14d
0x1400248b9  mov     edx, 900ACh; dwIoControlCode
0x1400248be  mov     [rsp+78h+nOutBufferSize], r14d; nOutBufferSize
0x1400248c3  mov     rcx, rbp; hDevice
0x1400248c6  mov     [rsp+78h+lpOutBuffer], r14; lpOutBuffer
0x1400248cb  mov     [rbx+4], r14w
0x1400248d0  call    cs:__imp_DeviceIoControl
0x1400248d6  test    eax, eax
0x1400248d8  jnz     short loc_14002488F
0x1400248da  call    HrGetLastFailure
0x1400248df  mov     edi, eax
0x1400248e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400248e8  lea     rax, WPP_GLOBAL_Control
0x1400248ef  cmp     rcx, rax
0x1400248f2  jz      short loc_140024912
0x1400248f4  test    byte ptr [rcx+1Ch], 1
0x1400248f8  jz      short loc_140024912
0x1400248fa  mov     rcx, [rcx+10h]
0x1400248fe  lea     r8, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids
0x140024905  mov     edx, 21h ; '!'
0x14002490a  mov     r9d, edi
0x14002490d  call    WPP_SF_d
0x140024912  mov     rcx, rbx; void *
0x140024915  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002491a  mov     eax, edi
0x14002491c  jmp     short loc_140024960
0x14002491e  mov     rcx, cs:WPP_GLOBAL_Control
0x140024925  lea     rax, WPP_GLOBAL_Control
0x14002492c  cmp     rcx, rax
0x14002492f  jz      short loc_14002494F
0x140024931  test    byte ptr [rcx+1Ch], 1
0x140024935  jz      short loc_14002494F
0x140024937  mov     rcx, [rcx+10h]
0x14002493b  lea     r8, WPP_b4906c3a21de3f4a53fa7ae74c12047f_Traceguids
0x140024942  mov     edx, 1Fh
0x140024947  mov     r9d, esi
0x14002494a  call    WPP_SF_d
0x14002494f  mov     rcx, [rsp+78h+lpInBuffer]; void *
0x140024954  test    rcx, rcx
0x140024957  jz      short loc_14002495E
0x140024959  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14002495e  mov     eax, esi
0x140024960  mov     rcx, [rsp+78h+var_28]
0x140024965  xor     rcx, rsp; StackCookie
0x140024968  call    __security_check_cookie
0x14002496d  lea     r11, [rsp+78h+var_18]
0x140024972  mov     rbx, [r11+28h]
0x140024976  mov     rbp, [r11+30h]
0x14002497a  mov     rsp, r11
0x14002497d  pop     r14
0x14002497f  pop     rdi
0x140024980  pop     rsi
0x140024981  retn
```
