# Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(ushort const *,_EVENT_TRACE_PROPERTIES const *,ushort const *,ulong,void *)

- ea: `0x1800398cc`
- end: `0x180039bad`
- name: `?StartTraceW@CEtwPrivateLogger@Performance@Windows@Microsoft@@QEAAJPEBGPEBU_EVENT_TRACE_PROPERTIES@@0KPEAX@Z`
- size: `737`
- prototype: `__int64 __usercall@<rax>(Microsoft::Windows::Performance::CEtwPrivateLogger *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const struct _EVENT_TRACE_PROPERTIES *@<r8>, const unsigned __int16 *@<r9>, unsigned int, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003ea2c`

## callees

- `0x18000829c`
- `0x180030de0`
- `0x1800351c0`
- `0x1800366b0`
- `0x1800398cc`
- `0x18004ab44`
- `0x18004ece0`
- `0x18004f964`
- `0x180074390`
- `0x1800747c0`
- `0x180082d3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180039b23`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180039b59`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180039b23`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180039b59`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180039b4a`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180039b4a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180039971`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180039971`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180039985`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180039985`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEtwPrivateLogger::StartTraceW(
        Microsoft::Windows::Performance::CEtwPrivateLogger *this,
        unsigned __int16 *a2,
        const struct _EVENT_TRACE_PROPERTIES *a3,
        const unsigned __int16 *a4,
        unsigned int Size,
        void *a6)
{
  __int64 result; // rax
  unsigned int v8; // edi
  int v9; // ecx
  unsigned __int64 v10; // r12
  unsigned int v11; // r14d
  unsigned int v12; // r13d
  void **v13; // rbx
  void *v14; // rdx
  __int128 v15; // xmm1
  __int128 v16; // xmm2
  __int128 v17; // xmm3
  __int128 v18; // xmm4
  __int128 v19; // xmm5
  __int128 v20; // xmm6
  __int64 v21; // xmm7_8
  _OWORD *v22; // rax
  HRESULT v23; // edi
  ULONG started; // edi
  unsigned int v25[2]; // [rsp+28h] [rbp-99h] BYREF
  const struct _EVENT_TRACE_PROPERTIES *v26; // [rsp+30h] [rbp-91h]
  void *Src; // [rsp+38h] [rbp-89h]
  unsigned __int16 *v28; // [rsp+40h] [rbp-81h]
  GUID pguid; // [rsp+48h] [rbp-79h] BYREF
  OLECHAR sz[8]; // [rsp+58h] [rbp-69h] BYREF
  __int128 v31; // [rsp+68h] [rbp-59h]
  __int128 v32; // [rsp+78h] [rbp-49h]
  _OWORD v33[2]; // [rsp+88h] [rbp-39h]

  v26 = a3;
  v28 = a2;
  Src = a6;
  if ( Size && !a6 )
    return 2147942487LL;
  *(_OWORD *)sz = *(_OWORD *)L"{28ad2447-105b-4fe2-9599-e59b2aa9a634}";
  v32 = *(_OWORD *)L"fe2-9599-e59b2aa9a634}";
  v31 = *(_OWORD *)L"7-105b-4fe2-9599-e59b2aa9a634}";
  v33[0] = *(_OWORD *)L"-e59b2aa9a634}";
  *(_OWORD *)((char *)v33 + 14) = *(_OWORD *)L"a9a634}";
  pguid = 0;
  CoCreateGuid(&pguid);
  StringFromGUID2(&pguid, sz, 39);
  v25[0] = 0;
  *(_QWORD *)&pguid.Data1 = 0;
  result = StringCchLengthW(sz, 0x400u, (unsigned __int64 *)&pguid.Data1);
  if ( (int)result >= 0 )
  {
    result = ULongLongToULong(*(unsigned __int64 *)&pguid.Data1, v25);
    if ( (int)result >= 0 )
    {
      v8 = Size + 120;
      if ( Size < 0xFFFFFF88 )
      {
        if ( (v8 & 1) != 0 )
        {
          v9 = v8 & 1;
          if ( v8 - v9 + 2 < v8 )
            return 2147942934LL;
          v8 = v8 - v9 + 2;
        }
        v10 = v25[0];
        pguid.Data1 = 0;
        result = ULongLongToULong(2LL * v25[0], &pguid.Data1);
        if ( (int)result < 0 )
          return result;
        v11 = v8 + pguid.Data1;
        if ( v8 + pguid.Data1 >= v8 )
        {
          pguid.Data1 = 0;
          result = ULongLongToULong(0x800u, &pguid.Data1);
          if ( (int)result < 0 )
            return result;
          v12 = v11 + pguid.Data1;
          if ( v11 + pguid.Data1 >= v11 )
          {
            v13 = (void **)((char *)this + 8);
            if ( !(unsigned __int8)ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(
                                     (char *)this + 8,
                                     v12) )
              return 2147942414LL;
            memset_0(*v13, 0, v12);
            v14 = Src;
            v15 = *(_OWORD *)&v26->Wnode.CountLost;
            v16 = *(_OWORD *)v26->Wnode.Guid.Data4;
            v17 = *(_OWORD *)&v26->BufferSize;
            v18 = *(_OWORD *)&v26->LogFileMode;
            v19 = *(_OWORD *)&v26->NumberOfBuffers;
            v20 = *(_OWORD *)&v26->LogBuffersLost;
            v21 = *(_QWORD *)&v26->LogFileNameOffset;
            v22 = *v13;
            *v22 = *(_OWORD *)&v26->Wnode.BufferSize;
            v22[1] = v15;
            v22[2] = v16;
            v22[3] = v17;
            v22[4] = v18;
            v22[5] = v19;
            v22[6] = v20;
            *((_QWORD *)v22 + 14) = v21;
            *(_DWORD *)*v13 = v12;
            *((_DWORD *)*v13 + 11) = 0x20000;
            *((_DWORD *)*v13 + 29) = v8;
            *((_DWORD *)*v13 + 28) = v11;
            if ( v14 )
              memcpy_0((char *)*v13 + 120, v14, Size);
            StringCchCopyNW((unsigned __int16 *)((char *)*v13 + v8), v10, sz, v10);
            StringCchCopyNW((unsigned __int16 *)((char *)*v13 + v11), 0x400u, v28, 0x400u);
            v23 = Microsoft::Windows::Performance::CEtwPrivateLogger::Register(this);
            if ( v23 >= 0 )
            {
              *(_OWORD *)((char *)*v13 + 24) = *((_OWORD *)this + 2);
              started = StartTraceW((PTRACEHANDLE)this, sz, (PEVENT_TRACE_PROPERTIES)*v13);
              if ( started )
              {
                free(*v13);
                *v13 = 0;
                Microsoft::Windows::Performance::CEtwPrivateLogger::Unregister(this);
              }
              return ATL::AtlHresultFromWin32(started);
            }
            else
            {
              free(*v13);
              result = (unsigned int)v23;
              *v13 = 0;
            }
            return result;
          }
        }
      }
      return 2147942934LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800398cc  mov     rax, rsp
0x1800398cf  mov     [rax+18h], rbx
0x1800398d3  push    rbp
0x1800398d4  push    rsi
0x1800398d5  push    rdi
0x1800398d6  push    r12
0x1800398d8  push    r13
0x1800398da  push    r14
0x1800398dc  push    r15
0x1800398de  lea     rbp, [rax-4Fh]
0x1800398e2  sub     rsp, 0D0h
0x1800398e9  movaps  xmmword ptr [rax-48h], xmm6
0x1800398ed  movaps  xmmword ptr [rax-58h], xmm7
0x1800398f1  mov     rax, cs:__security_cookie
0x1800398f8  xor     rax, rsp
0x1800398fb  mov     [rbp+47h+var_60], rax
0x1800398ff  mov     r15d, dword ptr [rbp+47h+Size]
0x180039903  xor     ebx, ebx
0x180039905  mov     rax, [rbp+47h+arg_28]
0x180039909  mov     rsi, rcx
0x18003990c  mov     [rsp+100h+var_D8], r8
0x180039911  mov     [rsp+100h+var_C8], rdx
0x180039916  mov     [rsp+100h+Src], rax
0x18003991b  test    r15d, r15d
0x18003991e  jz      short loc_18003992F
0x180039920  test    rax, rax
0x180039923  jnz     short loc_18003992F
0x180039925  mov     eax, 80070057h
0x18003992a  jmp     loc_180039B7C
0x18003992f  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f; "{28ad2447-105b-4fe2-9599-e59b2aa9a634}"
0x180039936  lea     rcx, [rbp+47h+pguid]; pguid
0x18003993a  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+10h; "7-105b-4fe2-9599-e59b2aa9a634}"
0x180039941  movaps  xmmword ptr [rbp+47h+sz], xmm0
0x180039945  movaps  xmm0, xmmword ptr cs:a28ad2447105b4f+20h; "fe2-9599-e59b2aa9a634}"
0x18003994c  movaps  [rbp+47h+var_90], xmm0
0x180039950  movups  xmm0, xmmword ptr cs:a28ad2447105b4f+3Eh; "a9a634}"
0x180039957  movaps  [rbp+47h+var_A0], xmm1
0x18003995b  movaps  xmm1, xmmword ptr cs:a28ad2447105b4f+30h; "-e59b2aa9a634}"
0x180039962  movaps  xmmword ptr [rbp+47h+var_80], xmm1
0x180039966  movups  xmmword ptr [rbp+47h+var_80+0Eh], xmm0
0x18003996a  xorps   xmm0, xmm0
0x18003996d  movups  xmmword ptr [rbp+47h+pguid.Data1], xmm0
0x180039971  call    cs:__imp_CoCreateGuid
0x180039977  mov     r8d, 27h ; '''; cchMax
0x18003997d  lea     rdx, [rbp+47h+sz]; lpsz
0x180039981  lea     rcx, [rbp+47h+pguid]; rguid
0x180039985  call    cs:__imp_StringFromGUID2
0x18003998b  lea     r8, [rbp+47h+pguid]; unsigned __int64 *
0x18003998f  mov     [rsp+100h+var_E0], ebx
0x180039993  mov     edx, 400h; unsigned __int64
0x180039998  mov     qword ptr [rbp+47h+pguid.Data1], rbx
0x18003999c  lea     rcx, [rbp+47h+sz]; unsigned __int16 *
0x1800399a0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800399a5  test    eax, eax
0x1800399a7  js      loc_180039B7C
0x1800399ad  mov     rcx, qword ptr [rbp+47h+pguid.Data1]; unsigned __int64
0x1800399b1  lea     rdx, [rsp+100h+var_E0]; unsigned int *
0x1800399b6  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800399bb  test    eax, eax
0x1800399bd  js      loc_180039B7C
0x1800399c3  lea     edi, [r15+78h]
0x1800399c7  cmp     edi, 78h ; 'x'
0x1800399ca  jb      loc_180039B77
0x1800399d0  mov     ecx, edi
0x1800399d2  and     ecx, 1
0x1800399d5  jz      short loc_1800399E8
0x1800399d7  mov     eax, edi
0x1800399d9  sub     eax, ecx
0x1800399db  add     eax, 2
0x1800399de  cmp     eax, edi
0x1800399e0  jb      loc_180039B77
0x1800399e6  mov     edi, eax
0x1800399e8  mov     r12d, [rsp+100h+var_E0]
0x1800399ed  lea     rdx, [rbp+47h+pguid]; unsigned int *
0x1800399f1  mov     [rbp+47h+pguid.Data1], ebx
0x1800399f4  lea     rcx, [r12+r12]; unsigned __int64
0x1800399f8  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800399fd  test    eax, eax
0x1800399ff  js      loc_180039B7C
0x180039a05  mov     r14d, [rbp+47h+pguid.Data1]
0x180039a09  add     r14d, edi
0x180039a0c  cmp     r14d, edi
0x180039a0f  jb      loc_180039B77
0x180039a15  lea     rdx, [rbp+47h+pguid]; unsigned int *
0x180039a19  mov     [rbp+47h+pguid.Data1], ebx
0x180039a1c  mov     ecx, 800h; unsigned __int64
0x180039a21  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180039a26  test    eax, eax
0x180039a28  js      loc_180039B7C
0x180039a2e  mov     r13d, [rbp+47h+pguid.Data1]
0x180039a32  add     r13d, r14d
0x180039a35  cmp     r13d, r14d
0x180039a38  jb      loc_180039B77
0x180039a3e  lea     rbx, [rsi+8]
0x180039a42  mov     edx, r13d
0x180039a45  mov     rcx, rbx
0x180039a48  call    ?AllocateBytes@?$CHeapPtrBase@U_TRACE_LOGFILE_HEADER@@VCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtrBase<_TRACE_LOGFILE_HEADER,ATL::CCRTAllocator>::AllocateBytes(unsigned __int64)
0x180039a4d  test    al, al
0x180039a4f  jnz     short loc_180039A5B
0x180039a51  mov     eax, 8007000Eh
0x180039a56  jmp     loc_180039B7C
0x180039a5b  mov     rcx, [rbx]; void *
0x180039a5e  xor     edx, edx; Val
0x180039a60  mov     r8d, r13d; Size
0x180039a63  call    memset_0
0x180039a68  mov     rax, [rsp+100h+var_D8]
0x180039a6d  mov     rdx, [rsp+100h+Src]; Src
0x180039a72  movaps  xmm0, xmmword ptr [rax]
0x180039a75  movaps  xmm1, xmmword ptr [rax+10h]
0x180039a79  movaps  xmm2, xmmword ptr [rax+20h]
0x180039a7d  movaps  xmm3, xmmword ptr [rax+30h]
0x180039a81  movaps  xmm4, xmmword ptr [rax+40h]
0x180039a85  movaps  xmm5, xmmword ptr [rax+50h]
0x180039a89  movaps  xmm6, xmmword ptr [rax+60h]
0x180039a8d  movsd   xmm7, qword ptr [rax+70h]
0x180039a92  mov     rax, [rbx]
0x180039a95  movups  xmmword ptr [rax], xmm0
0x180039a98  movups  xmmword ptr [rax+10h], xmm1
0x180039a9c  movups  xmmword ptr [rax+20h], xmm2
0x180039aa0  movups  xmmword ptr [rax+30h], xmm3
0x180039aa4  movups  xmmword ptr [rax+40h], xmm4
0x180039aa8  movups  xmmword ptr [rax+50h], xmm5
0x180039aac  movups  xmmword ptr [rax+60h], xmm6
0x180039ab0  movsd   qword ptr [rax+70h], xmm7
0x180039ab5  mov     rax, [rbx]
0x180039ab8  mov     [rax], r13d
0x180039abb  mov     rax, [rbx]
0x180039abe  mov     dword ptr [rax+2Ch], 20000h
0x180039ac5  mov     rax, [rbx]
0x180039ac8  mov     [rax+74h], edi
0x180039acb  mov     rax, [rbx]
0x180039ace  mov     [rax+70h], r14d
0x180039ad2  test    rdx, rdx
0x180039ad5  jz      short loc_180039AE6
0x180039ad7  mov     rcx, [rbx]
0x180039ada  mov     r8, r15; Size
0x180039add  add     rcx, 78h ; 'x'; void *
0x180039ae1  call    memcpy_0
0x180039ae6  mov     ecx, edi
0x180039ae8  lea     r8, [rbp+47h+sz]; unsigned __int16 *
0x180039aec  add     rcx, [rbx]; unsigned __int16 *
0x180039aef  mov     r9, r12; unsigned __int64
0x180039af2  mov     rdx, r12; unsigned __int64
0x180039af5  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180039afa  mov     r8, [rsp+100h+var_C8]; unsigned __int16 *
0x180039aff  mov     edx, 400h; unsigned __int64
0x180039b04  mov     ecx, r14d
0x180039b07  mov     r9d, edx; unsigned __int64
0x180039b0a  add     rcx, [rbx]; unsigned __int16 *
0x180039b0d  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180039b12  mov     rcx, rsi; this
0x180039b15  call    ?Register@CEtwPrivateLogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEtwPrivateLogger::Register(void)
0x180039b1a  mov     edi, eax
0x180039b1c  test    eax, eax
0x180039b1e  jns     short loc_180039B34
0x180039b20  mov     rcx, [rbx]; Block
0x180039b23  call    cs:__imp_free
0x180039b29  mov     eax, edi
0x180039b2b  mov     qword ptr [rbx], 0
0x180039b32  jmp     short loc_180039B7C
0x180039b34  mov     rax, [rbx]
0x180039b37  lea     rdx, [rbp+47h+sz]; InstanceName
0x180039b3b  movups  xmm0, xmmword ptr [rsi+20h]
0x180039b3f  mov     rcx, rsi; TraceHandle
0x180039b42  movdqu  xmmword ptr [rax+18h], xmm0
0x180039b47  mov     r8, [rbx]; Properties
0x180039b4a  call    cs:__imp_StartTraceW
0x180039b50  mov     edi, eax
0x180039b52  test    eax, eax
0x180039b54  jz      short loc_180039B6E
0x180039b56  mov     rcx, [rbx]; Block
0x180039b59  call    cs:__imp_free
0x180039b5f  mov     rcx, rsi; this
0x180039b62  mov     qword ptr [rbx], 0
0x180039b69  call    ?Unregister@CEtwPrivateLogger@Performance@Windows@Microsoft@@AEAAJXZ; Microsoft::Windows::Performance::CEtwPrivateLogger::Unregister(void)
0x180039b6e  mov     ecx, edi; unsigned int
0x180039b70  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180039b75  jmp     short loc_180039B7C
0x180039b77  mov     eax, 80070216h
0x180039b7c  mov     rcx, [rbp+47h+var_60]
0x180039b80  xor     rcx, rsp; StackCookie
0x180039b83  call    __security_check_cookie
0x180039b88  lea     r11, [rsp+100h+var_30]
0x180039b90  mov     rbx, [r11+50h]
0x180039b94  movaps  xmm6, xmmword ptr [r11-10h]
0x180039b99  movaps  xmm7, xmmword ptr [r11-20h]
0x180039b9e  mov     rsp, r11
0x180039ba1  pop     r15
0x180039ba3  pop     r14
0x180039ba5  pop     r13
0x180039ba7  pop     r12
0x180039ba9  pop     rdi
0x180039baa  pop     rsi
0x180039bab  pop     rbp
0x180039bac  retn
```
