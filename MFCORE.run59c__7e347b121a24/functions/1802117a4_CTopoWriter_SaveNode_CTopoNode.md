# CTopoWriter::SaveNode(CTopoNode *)

- ea: `0x1802117a4`
- end: `0x180211dd1`
- name: `?SaveNode@CTopoWriter@@QEAAJPEAVCTopoNode@@@Z`
- size: `1581`
- prototype: `int(CTopoWriter *__hidden this, struct CTopoNode *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1802c6d64`
- `0x1802c9a50`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x18012649c`
- `0x1802117a4`
- `0x180328260`
- `0x180328400`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021180c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802118e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021198e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180211a3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180211ae9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180211b9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180211c72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180211d19`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021180c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802118e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021198e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180211a3e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180211ae9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180211b9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180211c72`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180211d19`

## string_xrefs

- `0x1802117d3`: `CTopoWriter::SaveNode`
- `0x18021186a`: `CTopoWriter::SaveNode`
- `0x1802118b2`: `CTopoWriter::SaveNode`
- `0x180211940`: `CTopoWriter::SaveNode`
- `0x1802119ec`: `CTopoWriter::SaveNode`
- `0x180211a9c`: `CTopoWriter::SaveNode`
- `0x180211b47`: `CTopoWriter::SaveNode`
- `0x180211bfd`: `CTopoWriter::SaveNode`
- `0x180211c36`: `CTopoWriter::SaveNode`

## pseudocode

```c
__int64 __fastcall CTopoWriter::SaveNode(CTopoWriter *this, struct CTopoNode *a2)
{
  unsigned int v2; // r15d
  __int64 v5; // rdx
  int IdByPtr; // ebx
  __int64 v7; // r8
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  CBinaryWriter *v12; // rsi
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 *v25; // rcx
  CallStackTracing *v26; // rax
  struct CallStackContext *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rcx
  CallStackTracing *v41; // rax
  struct CallStackContext *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 *v45; // rcx
  CallStackTracing *v46; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v49; // [rsp+68h] [rbp+38h] BYREF
  unsigned int v50; // [rsp+70h] [rbp+40h] BYREF

  v2 = -1;
  v50 = -1;
  if ( !a2 )
  {
    v12 = (CTopoWriter *)((char *)this + 528);
LABEL_71:
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v49, "CTopoWriter::SaveNode", 574);
    IdByPtr = CBinaryWriter::WriteBool(v12, 1);
    if ( IdByPtr >= 0 )
    {
      IdByPtr = CBinaryWriter::WriteBool(v12, v2);
      if ( IdByPtr < 0 )
      {
        v45 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v46 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44);
          CallStackTracing::s_wpInstance = v46;
          if ( v46 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v46 + 8LL))(v46, 2032) )
          {
            v45 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v45 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v45 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v45);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != IdByPtr )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CTopoWriter::SaveNode", 575, IdByPtr);
        }
        if ( g_wppLevels )
        {
          v11 = 36;
          goto LABEL_93;
        }
      }
    }
    else
    {
      v40 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v38, v39);
        CallStackTracing::s_wpInstance = v41;
        if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
        {
          v40 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v40 + 8) )
      {
        v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v40);
        if ( *((_DWORD *)v42 + 499) != IdByPtr )
          CallStackContext::TraceFailure(v42, "CTopoWriter::SaveNode", 574, IdByPtr);
      }
      if ( g_wppLevels )
      {
        v11 = 35;
        goto LABEL_93;
      }
    }
    goto LABEL_94;
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v49, "CTopoWriter::SaveNode", 555);
  IdByPtr = CPersistStreamMap::FindIdByPtr((CTopoWriter *)((char *)this + 16), (struct IUnknown *)a2, &v50);
  if ( IdByPtr < 0 )
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5, v7);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != IdByPtr )
        CallStackContext::TraceFailure(v10, "CTopoWriter::SaveNode", 555, IdByPtr);
    }
    if ( g_wppLevels )
    {
      v11 = 29;
LABEL_93:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v11,
        &WPP_2f1a00f0f9c13228d867e3987ca5fdd2_Traceguids,
        this,
        IdByPtr);
      goto LABEL_94;
    }
    goto LABEL_94;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v49);
  v12 = (CTopoWriter *)((char *)this + 528);
  if ( IdByPtr != 1 )
  {
    v2 = v50;
    goto LABEL_71;
  }
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v49, "CTopoWriter::SaveNode", 564);
  IdByPtr = CBinaryWriter::WriteBool((CTopoWriter *)((char *)this + 528), 0);
  if ( IdByPtr >= 0 )
  {
    IdByPtr = CBinaryWriter::WriteBool((CTopoWriter *)((char *)this + 528), *((_DWORD *)a2 + 24));
    if ( IdByPtr >= 0 )
    {
      IdByPtr = CPersistStreamMap::MapPtrToId((CTopoWriter *)((char *)this + 16), (struct IUnknown *)a2, &v50);
      if ( IdByPtr >= 0 )
      {
        IdByPtr = CBinaryWriter::WriteBool((CTopoWriter *)((char *)this + 528), v50);
        if ( IdByPtr >= 0 )
        {
          IdByPtr = (*(__int64 (__fastcall **)(struct CTopoNode *, CTopoWriter *))(*(_QWORD *)a2 + 400LL))(a2, this);
          if ( IdByPtr < 0 )
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33, v34);
              CallStackTracing::s_wpInstance = v36;
              if ( v36
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
              {
                v35 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v35 = &qword_1803CE250;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
              }
            }
            if ( *((_BYTE *)v35 + 8) )
            {
              v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
              if ( *((_DWORD *)v37 + 499) != IdByPtr )
                CallStackContext::TraceFailure(v37, "CTopoWriter::SaveNode", 570, IdByPtr);
            }
            if ( g_wppLevels )
            {
              v11 = 34;
              goto LABEL_93;
            }
          }
        }
        else
        {
          v30 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
            CallStackTracing::s_wpInstance = v31;
            if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
            {
              v30 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v30 = &qword_1803CE250;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v30 + 8) )
          {
            v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
            if ( *((_DWORD *)v32 + 499) != IdByPtr )
              CallStackContext::TraceFailure(v32, "CTopoWriter::SaveNode", 569, IdByPtr);
          }
          if ( g_wppLevels )
          {
            v11 = 33;
            goto LABEL_93;
          }
        }
      }
      else
      {
        v25 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23, v24);
          CallStackTracing::s_wpInstance = v26;
          if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
          {
            v25 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v25 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v25 + 8) )
        {
          v27 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v25);
          if ( *((_DWORD *)v27 + 499) != IdByPtr )
            CallStackContext::TraceFailure(v27, "CTopoWriter::SaveNode", 567, IdByPtr);
        }
        if ( g_wppLevels )
        {
          v11 = 32;
          goto LABEL_93;
        }
      }
    }
    else
    {
      v20 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
        {
          v20 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v22 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
        if ( *((_DWORD *)v22 + 499) != IdByPtr )
          CallStackContext::TraceFailure(v22, "CTopoWriter::SaveNode", 565, IdByPtr);
      }
      if ( g_wppLevels )
      {
        v11 = 31;
        goto LABEL_93;
      }
    }
  }
  else
  {
    v15 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14);
      CallStackTracing::s_wpInstance = v16;
      if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v15 + 8) )
    {
      v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
      if ( *((_DWORD *)v17 + 499) != IdByPtr )
        CallStackContext::TraceFailure(v17, "CTopoWriter::SaveNode", 564, IdByPtr);
    }
    if ( g_wppLevels )
    {
      v11 = 30;
      goto LABEL_93;
    }
  }
LABEL_94:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v49);
  return (unsigned int)IdByPtr;
}

```

## disassembly

```asm
0x1802117a4  mov     [rsp-28h+arg_0], rbx
0x1802117a9  push    rbp
0x1802117aa  push    rsi
0x1802117ab  push    rdi
0x1802117ac  push    r14
0x1802117ae  push    r15
0x1802117b0  mov     rbp, rsp
0x1802117b3  sub     rsp, 30h
0x1802117b7  or      r15d, 0FFFFFFFFh
0x1802117bb  mov     r14, rdx
0x1802117be  mov     [rbp+arg_10], r15d
0x1802117c2  mov     rdi, rcx
0x1802117c5  test    rdx, rdx
0x1802117c8  jz      loc_180211C2F
0x1802117ce  mov     esi, 22Bh
0x1802117d3  lea     rdx, aCtopowriterSav; "CTopoWriter::SaveNode"
0x1802117da  mov     r8d, esi; int
0x1802117dd  lea     rcx, [rbp+arg_8]; this
0x1802117e1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802117e6  lea     r8, [rbp+arg_10]; unsigned int *
0x1802117ea  mov     rdx, r14; struct IUnknown *
0x1802117ed  lea     rcx, [rdi+10h]; this
0x1802117f1  call    ?FindIdByPtr@CPersistStreamMap@@UEAAJPEAUIUnknown@@PEAK@Z; CPersistStreamMap::FindIdByPtr(IUnknown *,ulong *)
0x1802117f6  mov     ebx, eax
0x1802117f8  test    eax, eax
0x1802117fa  jns     loc_180211893
0x180211800  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211807  test    rcx, rcx
0x18021180a  jnz     short loc_180211854
0x18021180c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180211813  nop     dword ptr [rax+rax+00h]
0x180211818  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18021181f  mov     rcx, rax
0x180211822  test    rax, rax
0x180211825  jz      short loc_180211846
0x180211827  mov     rax, [rax]
0x18021182a  mov     edx, 7F0h
0x18021182f  mov     rax, [rax+8]
0x180211833  call    cs:__guard_dispatch_icall_fptr
0x180211839  test    eax, eax
0x18021183b  jz      short loc_180211846
0x18021183d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211844  jmp     short loc_180211854
0x180211846  lea     rcx, qword_1803CE250; this
0x18021184d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180211854  cmp     byte ptr [rcx+8], 0
0x180211858  jz      short loc_18021187C
0x18021185a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18021185f  cmp     [rax+7CCh], ebx
0x180211865  jz      short loc_18021187C
0x180211867  mov     r9d, ebx; int
0x18021186a  lea     rdx, aCtopowriterSav; "CTopoWriter::SaveNode"
0x180211871  mov     r8d, esi; int
0x180211874  mov     rcx, rax; this
0x180211877  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18021187c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180211883  jb      loc_180211DB4
0x180211889  mov     edx, 1Dh
0x18021188e  jmp     loc_180211D96
0x180211893  lea     rcx, [rbp+arg_8]; this
0x180211897  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18021189c  lea     rsi, [rdi+210h]
0x1802118a3  cmp     ebx, 1
0x1802118a6  jnz     loc_180211C29
0x1802118ac  mov     r8d, 234h; int
0x1802118b2  lea     rdx, aCtopowriterSav; "CTopoWriter::SaveNode"
0x1802118b9  lea     rcx, [rbp+arg_8]; this
0x1802118bd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1802118c2  xor     edx, edx; int
0x1802118c4  mov     rcx, rsi; this
0x1802118c7  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x1802118cc  mov     ebx, eax
0x1802118ce  test    eax, eax
0x1802118d0  jns     loc_18021196C
0x1802118d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802118dd  test    rcx, rcx
0x1802118e0  jnz     short loc_18021192A
0x1802118e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1802118e9  nop     dword ptr [rax+rax+00h]
0x1802118ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802118f5  mov     rcx, rax
0x1802118f8  test    rax, rax
0x1802118fb  jz      short loc_18021191C
0x1802118fd  mov     rax, [rax]
0x180211900  mov     edx, 7F0h
0x180211905  mov     rax, [rax+8]
0x180211909  call    cs:__guard_dispatch_icall_fptr
0x18021190f  test    eax, eax
0x180211911  jz      short loc_18021191C
0x180211913  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18021191a  jmp     short loc_18021192A
0x18021191c  lea     rcx, qword_1803CE250; this
0x180211923  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18021192a  cmp     byte ptr [rcx+8], 0
0x18021192e  jz      short loc_180211955
0x180211930  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180211935  cmp     [rax+7CCh], ebx
0x18021193b  jz      short loc_180211955
0x18021193d  mov     r9d, ebx; int
0x180211940  lea     rdx, aCtopowriterSav; "CTopoWriter::SaveNode"
0x180211947  mov     r8d, 234h; int
0x18021194d  mov     rcx, rax; this
0x180211950  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180211955  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18021195c  jb      loc_180211DB4
0x180211962  mov     edx, 1Eh
0x180211967  jmp     loc_180211D96
0x18021196c  mov     edx, [r14+60h]; int
0x180211970  mov     rcx, rsi; this
0x180211973  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x180211978  mov     ebx, eax
0x18021197a  test    eax, eax
0x18021197c  jns     loc_180211A18
0x180211982  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211989  test    rcx, rcx
0x18021198c  jnz     short loc_1802119D6
0x18021198e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180211995  nop     dword ptr [rax+rax+00h]
0x18021199a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1802119a1  mov     rcx, rax
0x1802119a4  test    rax, rax
0x1802119a7  jz      short loc_1802119C8
0x1802119a9  mov     rax, [rax]
0x1802119ac  mov     edx, 7F0h
0x1802119b1  mov     rax, [rax+8]
0x1802119b5  call    cs:__guard_dispatch_icall_fptr
0x1802119bb  test    eax, eax
0x1802119bd  jz      short loc_1802119C8
0x1802119bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1802119c6  jmp     short loc_1802119D6
0x1802119c8  lea     rcx, qword_1803CE250; this
0x1802119cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1802119d6  cmp     byte ptr [rcx+8], 0
0x1802119da  jz      short loc_180211A01
0x1802119dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1802119e1  cmp     [rax+7CCh], ebx
0x1802119e7  jz      short loc_180211A01
0x1802119e9  mov     r9d, ebx; int
0x1802119ec  lea     rdx, aCtopowriterSav; "CTopoWriter::SaveNode"
0x1802119f3  mov     r8d, 235h; int
0x1802119f9  mov     rcx, rax; this
0x1802119fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180211a01  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180211a08  jb      loc_180211DB4
0x180211a0e  mov     edx, 1Fh
0x180211a13  jmp     loc_180211D96
0x180211a18  lea     r8, [rbp+arg_10]; unsigned int *
0x180211a1c  mov     rdx, r14; struct IUnknown *
0x180211a1f  lea     rcx, [rdi+10h]; this
0x180211a23  call    ?MapPtrToId@CPersistStreamMap@@UEAAJPEAUIUnknown@@PEAK@Z; CPersistStreamMap::MapPtrToId(IUnknown *,ulong *)
0x180211a28  mov     ebx, eax
0x180211a2a  test    eax, eax
0x180211a2c  jns     loc_180211AC8
0x180211a32  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211a39  test    rcx, rcx
0x180211a3c  jnz     short loc_180211A86
0x180211a3e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180211a45  nop     dword ptr [rax+rax+00h]
0x180211a4a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180211a51  mov     rcx, rax
0x180211a54  test    rax, rax
0x180211a57  jz      short loc_180211A78
0x180211a59  mov     rax, [rax]
0x180211a5c  mov     edx, 7F0h
0x180211a61  mov     rax, [rax+8]
0x180211a65  call    cs:__guard_dispatch_icall_fptr
0x180211a6b  test    eax, eax
0x180211a6d  jz      short loc_180211A78
0x180211a6f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211a76  jmp     short loc_180211A86
0x180211a78  lea     rcx, qword_1803CE250; this
0x180211a7f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180211a86  cmp     byte ptr [rcx+8], 0
0x180211a8a  jz      short loc_180211AB1
0x180211a8c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180211a91  cmp     [rax+7CCh], ebx
0x180211a97  jz      short loc_180211AB1
0x180211a99  mov     r9d, ebx; int
0x180211a9c  lea     rdx, aCtopowriterSav; "CTopoWriter::SaveNode"
0x180211aa3  mov     r8d, 237h; int
0x180211aa9  mov     rcx, rax; this
0x180211aac  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180211ab1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180211ab8  jb      loc_180211DB4
0x180211abe  mov     edx, 20h ; ' '
0x180211ac3  jmp     loc_180211D96
0x180211ac8  mov     edx, [rbp+arg_10]; int
0x180211acb  mov     rcx, rsi; this
0x180211ace  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x180211ad3  mov     ebx, eax
0x180211ad5  test    eax, eax
0x180211ad7  jns     loc_180211B73
0x180211add  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211ae4  test    rcx, rcx
0x180211ae7  jnz     short loc_180211B31
0x180211ae9  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180211af0  nop     dword ptr [rax+rax+00h]
0x180211af5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180211afc  mov     rcx, rax
0x180211aff  test    rax, rax
0x180211b02  jz      short loc_180211B23
0x180211b04  mov     rax, [rax]
0x180211b07  mov     edx, 7F0h
0x180211b0c  mov     rax, [rax+8]
0x180211b10  call    cs:__guard_dispatch_icall_fptr
0x180211b16  test    eax, eax
0x180211b18  jz      short loc_180211B23
0x180211b1a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211b21  jmp     short loc_180211B31
0x180211b23  lea     rcx, qword_1803CE250; this
0x180211b2a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180211b31  cmp     byte ptr [rcx+8], 0
0x180211b35  jz      short loc_180211B5C
0x180211b37  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180211b3c  cmp     [rax+7CCh], ebx
0x180211b42  jz      short loc_180211B5C
0x180211b44  mov     r9d, ebx; int
0x180211b47  lea     rdx, aCtopowriterSav; "CTopoWriter::SaveNode"
0x180211b4e  mov     r8d, 239h; int
0x180211b54  mov     rcx, rax; this
0x180211b57  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180211b5c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180211b63  jb      loc_180211DB4
0x180211b69  mov     edx, 21h ; '!'
0x180211b6e  jmp     loc_180211D96
0x180211b73  mov     rax, [r14]
0x180211b76  mov     rdx, rdi
0x180211b79  mov     rcx, r14
0x180211b7c  mov     rax, [rax+190h]
0x180211b83  call    cs:__guard_dispatch_icall_fptr
0x180211b89  mov     ebx, eax
0x180211b8b  test    eax, eax
0x180211b8d  jns     loc_180211DB4
0x180211b93  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211b9a  test    rcx, rcx
0x180211b9d  jnz     short loc_180211BE7
0x180211b9f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180211ba6  nop     dword ptr [rax+rax+00h]
0x180211bab  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180211bb2  mov     rcx, rax
0x180211bb5  test    rax, rax
0x180211bb8  jz      short loc_180211BD9
0x180211bba  mov     rax, [rax]
0x180211bbd  mov     edx, 7F0h
0x180211bc2  mov     rax, [rax+8]
0x180211bc6  call    cs:__guard_dispatch_icall_fptr
0x180211bcc  test    eax, eax
0x180211bce  jz      short loc_180211BD9
0x180211bd0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211bd7  jmp     short loc_180211BE7
0x180211bd9  lea     rcx, qword_1803CE250; this
0x180211be0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180211be7  cmp     byte ptr [rcx+8], 0
0x180211beb  jz      short loc_180211C12
0x180211bed  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180211bf2  cmp     [rax+7CCh], ebx
0x180211bf8  jz      short loc_180211C12
0x180211bfa  mov     r9d, ebx; int
0x180211bfd  lea     rdx, aCtopowriterSav; "CTopoWriter::SaveNode"
0x180211c04  mov     r8d, 23Ah; int
0x180211c0a  mov     rcx, rax; this
0x180211c0d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180211c12  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180211c19  jb      loc_180211DB4
0x180211c1f  mov     edx, 22h ; '"'
0x180211c24  jmp     loc_180211D96
0x180211c29  mov     r15d, [rbp+arg_10]
0x180211c2d  jmp     short loc_180211C36
0x180211c2f  lea     rsi, [rcx+210h]
0x180211c36  lea     r14, aCtopowriterSav; "CTopoWriter::SaveNode"
0x180211c3d  mov     r8d, 23Eh; int
0x180211c43  mov     rdx, r14; char *
0x180211c46  lea     rcx, [rbp+arg_8]; this
0x180211c4a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180211c4f  mov     edx, 1; int
0x180211c54  mov     rcx, rsi; this
0x180211c57  call    ?WriteBool@CBinaryWriter@@QEAAJH@Z; CBinaryWriter::WriteBool(int)
0x180211c5c  mov     ebx, eax
0x180211c5e  test    eax, eax
0x180211c60  jns     loc_180211CF8
0x180211c66  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211c6d  test    rcx, rcx
0x180211c70  jnz     short loc_180211CBA
0x180211c72  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180211c79  nop     dword ptr [rax+rax+00h]
0x180211c7e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180211c85  mov     rcx, rax
0x180211c88  test    rax, rax
0x180211c8b  jz      short loc_180211CAC
0x180211c8d  mov     rax, [rax]
0x180211c90  mov     edx, 7F0h
0x180211c95  mov     rax, [rax+8]
0x180211c99  call    cs:__guard_dispatch_icall_fptr
0x180211c9f  test    eax, eax
0x180211ca1  jz      short loc_180211CAC
0x180211ca3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180211caa  jmp     short loc_180211CBA
0x180211cac  lea     rcx, qword_1803CE250; this
0x180211cb3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180211cba  cmp     byte ptr [rcx+8], 0
  ... truncated ...
```
