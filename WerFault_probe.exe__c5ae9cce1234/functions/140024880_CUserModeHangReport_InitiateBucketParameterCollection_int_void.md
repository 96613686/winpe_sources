# CUserModeHangReport::_InitiateBucketParameterCollection(int,void *)

- ea: `0x140024880`
- end: `0x140024979`
- name: `?_InitiateBucketParameterCollection@CUserModeHangReport@@AEAAJHPEAX@Z`
- size: `249`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this, int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400258c0`

## callees

- `0x14001444c`
- `0x140014474`
- `0x140024880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024927`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024927`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400248f3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400248f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024911`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024911`

## pseudocode

```c
__int64 __fastcall CUserModeHangReport::_InitiateBucketParameterCollection(CUserModeHangReport *this, int a2, void *a3)
{
  HANDLE Thread; // rax
  void *v6; // rcx
  signed int LastError; // eax
  unsigned int v8; // ebx

  if ( *((_DWORD *)this + 15) )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
    }
    return 2147943623LL;
  }
  else
  {
    *((_QWORD *)this + 3117) = a3;
    *((_DWORD *)this + 6232) = a2;
    Thread = CreateThread(0, 0, CUserModeHangReport::StaticBucketingThreadProc, this, 0, 0);
    v6 = (void *)*((_QWORD *)this + 3088);
    *((_QWORD *)this + 3088) = Thread;
    if ( (unsigned __int64)v6 + 1 > 1 )
      CloseHandle(v6);
    if ( *((_QWORD *)this + 3088) == -1 || *((_QWORD *)this + 3088) == 0 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, v8);
      }
    }
    else
    {
      return 0;
    }
    return v8;
  }
}

```

## disassembly

```asm
0x140024880  push    rbx
0x140024882  sub     rsp, 30h
0x140024886  cmp     dword ptr [rcx+3Ch], 0
0x14002488a  mov     rbx, rcx
0x14002488d  jz      short loc_1400248C7
0x14002488f  mov     rcx, cs:WPP_GLOBAL_Control
0x140024896  lea     rax, WPP_GLOBAL_Control
0x14002489d  cmp     rcx, rax
0x1400248a0  jz      short loc_1400248BD
0x1400248a2  test    byte ptr [rcx+1Ch], 8
0x1400248a6  jz      short loc_1400248BD
0x1400248a8  mov     rcx, [rcx+10h]
0x1400248ac  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400248b3  mov     edx, 0Dh
0x1400248b8  call    WPP_SF_
0x1400248bd  mov     eax, 800704C7h
0x1400248c2  jmp     loc_140024973
0x1400248c7  mov     [rcx+6168h], r8
0x1400248ce  mov     r9, rbx; lpParameter
0x1400248d1  mov     [rcx+6160h], edx
0x1400248d7  lea     r8, ?StaticBucketingThreadProc@CUserModeHangReport@@CAKPEAX@Z; lpStartAddress
0x1400248de  xor     edx, edx; dwStackSize
0x1400248e0  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1400248e9  xor     ecx, ecx; lpThreadAttributes
0x1400248eb  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1400248f3  call    cs:__imp_CreateThread
0x1400248f9  mov     rcx, [rbx+6080h]; hObject
0x140024900  mov     [rbx+6080h], rax
0x140024907  lea     rax, [rcx+1]
0x14002490b  cmp     rax, 1
0x14002490f  jbe     short loc_140024917
0x140024911  call    cs:__imp_CloseHandle
0x140024917  mov     rax, [rbx+6080h]
0x14002491e  inc     rax
0x140024921  cmp     rax, 1
0x140024925  ja      short loc_14002496F
0x140024927  call    cs:__imp_GetLastError
0x14002492d  mov     ebx, eax
0x14002492f  test    eax, eax
0x140024931  jle     short loc_14002493C
0x140024933  movzx   ebx, ax
0x140024936  or      ebx, 80070000h
0x14002493c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024943  lea     rax, WPP_GLOBAL_Control
0x14002494a  cmp     rcx, rax
0x14002494d  jz      short loc_140024971
0x14002494f  test    byte ptr [rcx+1Ch], 1
0x140024953  jz      short loc_140024971
0x140024955  mov     rcx, [rcx+10h]
0x140024959  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140024960  mov     edx, 0Eh
0x140024965  mov     r9d, ebx
0x140024968  call    WPP_SF_d
0x14002496d  jmp     short loc_140024971
0x14002496f  xor     ebx, ebx
0x140024971  mov     eax, ebx
0x140024973  add     rsp, 30h
0x140024977  pop     rbx
0x140024978  retn
```
