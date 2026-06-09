# CUserModeHangReport::_InitiateBucketParameterCollection(int,void *)

- ea: `0x140026100`
- end: `0x14002620c`
- name: `?_InitiateBucketParameterCollection@CUserModeHangReport@@AEAAJHPEAX@Z`
- size: `268`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this, int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400271e0`

## callees

- `0x140014ee4`
- `0x140014f14`
- `0x140026100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261b3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140026173`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140026173`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026197`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140026197`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids);
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, v8);
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
0x140026100  push    rbx
0x140026102  sub     rsp, 30h
0x140026106  cmp     dword ptr [rcx+3Ch], 0
0x14002610a  mov     rbx, rcx
0x14002610d  jz      short loc_140026147
0x14002610f  mov     rcx, cs:WPP_GLOBAL_Control
0x140026116  lea     rax, WPP_GLOBAL_Control
0x14002611d  cmp     rcx, rax
0x140026120  jz      short loc_14002613D
0x140026122  test    byte ptr [rcx+1Ch], 8
0x140026126  jz      short loc_14002613D
0x140026128  mov     rcx, [rcx+10h]
0x14002612c  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140026133  mov     edx, 0Dh
0x140026138  call    WPP_SF_
0x14002613d  mov     eax, 800704C7h
0x140026142  jmp     loc_140026205
0x140026147  mov     [rcx+6168h], r8
0x14002614e  mov     r9, rbx; lpParameter
0x140026151  mov     [rcx+6160h], edx
0x140026157  lea     r8, ?StaticBucketingThreadProc@CUserModeHangReport@@CAKPEAX@Z; lpStartAddress
0x14002615e  xor     edx, edx; dwStackSize
0x140026160  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x140026169  xor     ecx, ecx; lpThreadAttributes
0x14002616b  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140026173  call    cs:__imp_CreateThread
0x14002617a  nop     dword ptr [rax+rax+00h]
0x14002617f  mov     rcx, [rbx+6080h]; hObject
0x140026186  mov     [rbx+6080h], rax
0x14002618d  lea     rax, [rcx+1]
0x140026191  cmp     rax, 1
0x140026195  jbe     short loc_1400261A3
0x140026197  call    cs:__imp_CloseHandle
0x14002619e  nop     dword ptr [rax+rax+00h]
0x1400261a3  mov     rax, [rbx+6080h]
0x1400261aa  inc     rax
0x1400261ad  cmp     rax, 1
0x1400261b1  ja      short loc_140026201
0x1400261b3  call    cs:__imp_GetLastError
0x1400261ba  nop     dword ptr [rax+rax+00h]
0x1400261bf  mov     ebx, eax
0x1400261c1  test    eax, eax
0x1400261c3  jle     short loc_1400261CE
0x1400261c5  movzx   ebx, ax
0x1400261c8  or      ebx, 80070000h
0x1400261ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1400261d5  lea     rax, WPP_GLOBAL_Control
0x1400261dc  cmp     rcx, rax
0x1400261df  jz      short loc_140026203
0x1400261e1  test    byte ptr [rcx+1Ch], 1
0x1400261e5  jz      short loc_140026203
0x1400261e7  mov     rcx, [rcx+10h]
0x1400261eb  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x1400261f2  mov     edx, 0Eh
0x1400261f7  mov     r9d, ebx
0x1400261fa  call    WPP_SF_d
0x1400261ff  jmp     short loc_140026203
0x140026201  xor     ebx, ebx
0x140026203  mov     eax, ebx
0x140026205  add     rsp, 30h
0x140026209  pop     rbx
0x14002620a  retn
```
