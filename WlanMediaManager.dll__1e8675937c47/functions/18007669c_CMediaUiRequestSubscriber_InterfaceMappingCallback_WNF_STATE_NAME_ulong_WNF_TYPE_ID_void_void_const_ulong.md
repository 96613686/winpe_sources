# CMediaUiRequestSubscriber::InterfaceMappingCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x18007669c`
- end: `0x1800767e7`
- name: `?InterfaceMappingCallback@CMediaUiRequestSubscriber@@AEAAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `331`
- prototype: `__int64 __usercall@<rax>(CMediaUiRequestSubscriber *__hidden this@<rcx>, struct _WNF_STATE_NAME@<rdx>, unsigned int@<r8d>, struct _WNF_TYPE_ID *@<r9>, void *, const void *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800764e4`
- `0x1800767f0`

## callees

- `0x180076338`
- `0x18007669c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800767ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800767ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076704`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076704`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007675b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180076794`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18007675b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180076794`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMediaUiRequestSubscriber::InterfaceMappingCallback(
        CMediaUiRequestSubscriber *this,
        struct _WNF_STATE_NAME a2,
        __int64 a3,
        struct _WNF_TYPE_ID *a4,
        void *a5,
        char *a6,
        unsigned int a7)
{
  FILETIME *v8; // r15
  unsigned int v9; // edi
  char v10; // r14
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  unsigned int v12; // edi
  unsigned int v13; // ebp
  char *v14; // r12
  __int64 v15; // r14
  __int64 v16; // rax
  const FILETIME *v17; // r13
  int v18; // eax
  char v20; // [rsp+70h] [rbp+18h]
  FILETIME FileTime1; // [rsp+78h] [rbp+20h] BYREF

  FileTime1 = (FILETIME)a4;
  v8 = (FILETIME *)((char *)this + 88);
  FileTime1 = (FILETIME)*((_QWORD *)this + 11);
  if ( !*((_DWORD *)this + 5) )
  {
    v9 = a7;
    if ( a7 )
    {
      if ( (a7 & 0x1F) == 0 )
      {
        v10 = 0;
        v20 = 0;
        v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        v12 = v9 >> 5;
        v13 = 0;
        v14 = a6;
        while ( v13 < v12 )
        {
          if ( *((_DWORD *)this + 5) )
            goto LABEL_20;
          v15 = 32LL * v13;
          v16 = *(_QWORD *)&v14[v15] - NullGuid;
          if ( !v16 )
            v16 = *(_QWORD *)&v14[v15 + 8];
          if ( !v16 )
          {
            v10 = v20;
            break;
          }
          v17 = (const FILETIME *)&v14[v15];
          if ( CompareFileTime(v8, (const FILETIME *)&v14[v15 + 24]) >= 0 )
          {
            v10 = v20;
          }
          else
          {
            v18 = CMediaUiRequestSubscriber::AddInterfaceStateSubscription(
                    this,
                    *(struct _WNF_STATE_NAME *)&v14[v15 + 16]);
            v10 = v20;
            if ( v18 < 0 )
              v10 = 1;
            v20 = v10;
            if ( CompareFileTime(&FileTime1, v17 + 3) < 0 )
              FileTime1 = v17[3];
          }
          ++v13;
        }
        if ( !v10 )
          *v8 = FileTime1;
LABEL_20:
        LeaveCriticalSection(v11);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007669c  mov     r11, rsp
0x18007669f  mov     [r11+8], rbx
0x1800766a3  mov     [r11+20h], r9
0x1800766a7  mov     [r11+18h], r8d
0x1800766ab  mov     [r11+10h], rdx
0x1800766af  push    rbp
0x1800766b0  push    rsi
0x1800766b1  push    rdi
0x1800766b2  push    r12
0x1800766b4  push    r13
0x1800766b6  push    r14
0x1800766b8  push    r15
0x1800766ba  sub     rsp, 20h
0x1800766be  mov     rsi, rcx
0x1800766c1  lea     r15, [rcx+58h]
0x1800766c5  mov     rax, [r15]
0x1800766c8  mov     [r11+20h], rax
0x1800766cc  mov     eax, [rcx+14h]
0x1800766cf  test    eax, eax
0x1800766d1  jnz     loc_1800767D0
0x1800766d7  mov     edi, [rsp+58h+arg_30]
0x1800766de  test    edi, edi
0x1800766e0  jz      loc_1800767D0
0x1800766e6  test    dil, 1Fh
0x1800766ea  jnz     loc_1800767D0
0x1800766f0  xor     r14b, r14b
0x1800766f3  mov     [rsp+58h+arg_10], r14d
0x1800766f8  lea     rbx, [rcx+20h]
0x1800766fc  mov     [rsp+58h+arg_8], rbx
0x180076701  mov     rcx, rbx; lpCriticalSection
0x180076704  call    cs:__imp_EnterCriticalSection
0x18007670a  nop
0x18007670b  shr     edi, 5
0x18007670e  xor     ebp, ebp
0x180076710  mov     r12, [rsp+58h+arg_28]
0x180076718  cmp     ebp, edi
0x18007671a  jnb     loc_1800767BA
0x180076720  mov     eax, [rsi+14h]
0x180076723  test    eax, eax
0x180076725  jnz     loc_1800767C7
0x18007672b  mov     r14d, ebp
0x18007672e  shl     r14, 5
0x180076732  mov     rax, [r14+r12]
0x180076736  sub     rax, cs:NullGuid
0x18007673d  jnz     short loc_18007674B
0x18007673f  mov     rax, [r14+r12+8]
0x180076744  sub     rax, cs:qword_18009DE50
0x18007674b  test    rax, rax
0x18007674e  jz      short loc_1800767B5
0x180076750  lea     r13, [r14+r12]
0x180076754  lea     rdx, [r13+18h]; lpFileTime2
0x180076758  mov     rcx, r15; lpFileTime1
0x18007675b  call    cs:__imp_CompareFileTime
0x180076761  test    eax, eax
0x180076763  jns     short loc_1800767A9
0x180076765  mov     rdx, [r14+r12+10h]; struct _WNF_STATE_NAME
0x18007676a  mov     rcx, rsi; this
0x18007676d  call    ?AddInterfaceStateSubscription@CMediaUiRequestSubscriber@@AEAAJU_WNF_STATE_NAME@@@Z; CMediaUiRequestSubscriber::AddInterfaceStateSubscription(_WNF_STATE_NAME)
0x180076772  mov     r14d, [rsp+58h+arg_10]
0x180076777  movzx   r14d, r14b
0x18007677b  test    eax, eax
0x18007677d  mov     eax, 1
0x180076782  cmovs   r14d, eax
0x180076786  mov     [rsp+58h+arg_10], r14d
0x18007678b  lea     rdx, [r13+18h]; lpFileTime2
0x18007678f  lea     rcx, [rsp+58h+FileTime1]; lpFileTime1
0x180076794  call    cs:__imp_CompareFileTime
0x18007679a  test    eax, eax
0x18007679c  jns     short loc_1800767AE
0x18007679e  mov     rax, [r13+18h]
0x1800767a2  mov     qword ptr [rsp+58h+FileTime1.dwLowDateTime], rax
0x1800767a7  jmp     short loc_1800767AE
0x1800767a9  mov     r14d, [rsp+58h+arg_10]
0x1800767ae  inc     ebp
0x1800767b0  jmp     loc_180076718
0x1800767b5  mov     r14d, [rsp+58h+arg_10]
0x1800767ba  test    r14b, r14b
0x1800767bd  jnz     short loc_1800767C7
0x1800767bf  mov     rax, qword ptr [rsp+58h+FileTime1.dwLowDateTime]
0x1800767c4  mov     [r15], rax
0x1800767c7  mov     rcx, rbx; lpCriticalSection
0x1800767ca  call    cs:__imp_LeaveCriticalSection
0x1800767d0  xor     eax, eax
0x1800767d2  mov     rbx, [rsp+58h+arg_0]
0x1800767d7  add     rsp, 20h
0x1800767db  pop     r15
0x1800767dd  pop     r14
0x1800767df  pop     r13
0x1800767e1  pop     r12
0x1800767e3  pop     rdi
0x1800767e4  pop     rsi
0x1800767e5  pop     rbp
0x1800767e6  retn
```
