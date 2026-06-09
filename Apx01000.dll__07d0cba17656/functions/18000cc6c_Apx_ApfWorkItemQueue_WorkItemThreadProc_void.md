# Apx::ApfWorkItemQueue::WorkItemThreadProc(void)

- ea: `0x18000cc6c`
- end: `0x18000ce25`
- name: `?WorkItemThreadProc@ApfWorkItemQueue@Apx@@AEAAXXZ`
- size: `441`
- prototype: `void __fastcall(Apx::ApfWorkItemQueue *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d0d0`

## callees

- `0x18000a12c`
- `0x18000cc6c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cd8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ccf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ccf5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000ccd5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000ccd5`

## pseudocode

```c
void __fastcall Apx::ApfWorkItemQueue::WorkItemThreadProc(Apx::ApfWorkItemQueue *this)
{
  DWORD v2; // eax
  int v3; // ebp
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  bool v11; // zf
  HANDLE Handles[7]; // [rsp+20h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids);
  }
  Handles[0] = *((HANDLE *)this + 12);
  Handles[1] = *((HANDLE *)this + 11);
  while ( 1 )
  {
    v2 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( !v2 )
      break;
    if ( v2 == 1 )
    {
      do
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
        if ( *((_QWORD *)this + 10) )
        {
          v3 = 0;
          v6 = *((_QWORD *)this + 9) & 1LL;
          v7 = *(_QWORD *)(*((_QWORD *)this + 7) + 8 * ((*((_QWORD *)this + 8) - 1LL) & (*((_QWORD *)this + 9) >> 1)));
          v5 = *(_QWORD *)(v7 + 8 * v6);
          *(_QWORD *)(v7 + 8 * v6) = 0;
          v8 = *((_QWORD *)this + 9) & 1LL;
          v9 = *(_QWORD *)(*((_QWORD *)this + 7) + 8 * ((*((_QWORD *)this + 8) - 1LL) & (*((_QWORD *)this + 9) >> 1)));
          v10 = *(_QWORD *)(v9 + 8 * v8);
          *(_QWORD *)(v9 + 8 * v8) = 0;
          if ( v10 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 8LL))(v10, 1);
          v11 = (*((_QWORD *)this + 10))-- == 1;
          v4 = v5;
          if ( v11 )
            *((_QWORD *)this + 9) = 0;
          else
            ++*((_QWORD *)this + 9);
        }
        else
        {
          v3 = 1;
          v4 = 0;
          v5 = 0;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
        if ( !v3 )
        {
          (**(void (__fastcall ***)(__int64, Apx::ApfWorkItemQueue *))v5)(v5, this);
          v4 = v5 & -(__int64)((*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5) != 0);
        }
        if ( v4 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 8LL))(v4, 1);
      }
      while ( !v3 );
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids);
  }
}

```

## disassembly

```asm
0x18000cc6c  mov     [rsp+arg_10], rbx
0x18000cc71  push    rbp
0x18000cc72  push    rsi
0x18000cc73  push    rdi
0x18000cc74  push    r13
0x18000cc76  push    r14
0x18000cc78  sub     rsp, 30h
0x18000cc7c  mov     rbx, rcx
0x18000cc7f  lea     r13, WPP_GLOBAL_Control
0x18000cc86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc8d  cmp     rcx, r13
0x18000cc90  jz      short loc_18000CCB3
0x18000cc92  test    byte ptr [rcx+1Ch], 1
0x18000cc96  jz      short loc_18000CCB3
0x18000cc98  cmp     byte ptr [rcx+19h], 5
0x18000cc9c  jb      short loc_18000CCB3
0x18000cc9e  mov     edx, 16h
0x18000cca3  lea     r8, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids
0x18000ccaa  mov     rcx, [rcx+10h]
0x18000ccae  call    WPP_SF_
0x18000ccb3  mov     rax, [rbx+60h]
0x18000ccb7  mov     [rsp+58h+Handles], rax
0x18000ccbc  mov     rax, [rbx+58h]
0x18000ccc0  mov     [rsp+58h+var_30], rax
0x18000ccc5  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000ccc9  xor     r8d, r8d; bWaitAll
0x18000cccc  lea     rdx, [rsp+58h+Handles]; lpHandles
0x18000ccd1  lea     ecx, [r8+2]; nCount
0x18000ccd5  call    cs:__imp_WaitForMultipleObjects
0x18000ccdb  test    eax, eax
0x18000ccdd  jz      loc_18000CDE7
0x18000cce3  cmp     eax, 1
0x18000cce6  jnz     short loc_18000CCC5
0x18000cce8  mov     [rsp+58h+arg_0], 0
0x18000ccf1  lea     rcx, [rbx+8]; lpCriticalSection
0x18000ccf5  call    cs:__imp_EnterCriticalSection
0x18000ccfb  cmp     qword ptr [rbx+50h], 0
0x18000cd00  jnz     short loc_18000CD0D
0x18000cd02  mov     ebp, 1
0x18000cd07  xor     esi, esi
0x18000cd09  xor     edi, edi
0x18000cd0b  jmp     short loc_18000CD8B
0x18000cd0d  xor     ebp, ebp
0x18000cd0f  mov     rdx, [rbx+48h]
0x18000cd13  mov     rcx, rdx
0x18000cd16  shr     rcx, 1
0x18000cd19  mov     rax, [rbx+40h]
0x18000cd1d  dec     rax
0x18000cd20  and     rcx, rax
0x18000cd23  mov     rax, [rbx+38h]
0x18000cd27  and     edx, 1
0x18000cd2a  mov     rcx, [rax+rcx*8]
0x18000cd2e  mov     rdi, [rcx+rdx*8]
0x18000cd32  mov     [rcx+rdx*8], rbp
0x18000cd36  mov     [rsp+58h+arg_0], rdi
0x18000cd3b  mov     r8, [rbx+48h]
0x18000cd3f  mov     rdx, r8
0x18000cd42  shr     rdx, 1
0x18000cd45  mov     rax, [rbx+40h]
0x18000cd49  dec     rax
0x18000cd4c  and     rdx, rax
0x18000cd4f  mov     rax, [rbx+38h]
0x18000cd53  and     r8d, 1
0x18000cd57  mov     rdx, [rax+rdx*8]
0x18000cd5b  mov     rcx, [rdx+r8*8]
0x18000cd5f  mov     [rdx+r8*8], rbp
0x18000cd63  test    rcx, rcx
0x18000cd66  jz      short loc_18000CD77
0x18000cd68  mov     rax, [rcx]
0x18000cd6b  lea     edx, [rbp+1]
0x18000cd6e  mov     rax, [rax+8]
0x18000cd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd77  sub     qword ptr [rbx+50h], 1
0x18000cd7c  mov     rsi, rdi
0x18000cd7f  jnz     short loc_18000CD87
0x18000cd81  mov     [rbx+48h], rbp
0x18000cd85  jmp     short loc_18000CD8B
0x18000cd87  inc     qword ptr [rbx+48h]
0x18000cd8b  lea     rcx, [rbx+8]; lpCriticalSection
0x18000cd8f  call    cs:__imp_LeaveCriticalSection
0x18000cd95  test    ebp, ebp
0x18000cd97  jnz     short loc_18000CDC1
0x18000cd99  mov     rax, [rdi]
0x18000cd9c  mov     rdx, rbx
0x18000cd9f  mov     rcx, rdi
0x18000cda2  mov     rax, [rax]
0x18000cda5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdaa  mov     rax, [rdi]
0x18000cdad  mov     rcx, rdi
0x18000cdb0  mov     rax, [rax+10h]
0x18000cdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdb9  neg     al
0x18000cdbb  sbb     rsi, rsi
0x18000cdbe  and     rsi, rdi
0x18000cdc1  test    rsi, rsi
0x18000cdc4  jz      short loc_18000CDDA
0x18000cdc6  mov     rax, [rsi]
0x18000cdc9  mov     edx, 1
0x18000cdce  mov     rcx, rsi
0x18000cdd1  mov     rax, [rax+8]
0x18000cdd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdda  test    ebp, ebp
0x18000cddc  jz      loc_18000CCE8
0x18000cde2  jmp     loc_18000CCC5
0x18000cde7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cdee  cmp     rcx, r13
0x18000cdf1  jz      short loc_18000CE14
0x18000cdf3  test    byte ptr [rcx+1Ch], 1
0x18000cdf7  jz      short loc_18000CE14
0x18000cdf9  cmp     byte ptr [rcx+19h], 5
0x18000cdfd  jb      short loc_18000CE14
0x18000cdff  mov     edx, 17h
0x18000ce04  lea     r8, WPP_4b563394a57b3e3f8cbf98ece6690050_Traceguids
0x18000ce0b  mov     rcx, [rcx+10h]
0x18000ce0f  call    WPP_SF_
0x18000ce14  mov     rbx, [rsp+58h+arg_10]
0x18000ce19  add     rsp, 30h
0x18000ce1d  pop     r14
0x18000ce1f  pop     r13
0x18000ce21  pop     rdi
0x18000ce22  pop     rsi
0x18000ce23  pop     rbp
0x18000ce24  retn
```
