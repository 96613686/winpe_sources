# _TraceString(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,char *)

- ea: `0x180010fd0`
- end: `0x180011136`
- name: `?_TraceString@@YAXW4TraceSource@@EPEBGK1J1PEAD@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000ad90`

## callees

- `0x180010c8c`
- `0x180010fd0`
- `0x18001135c`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180011016`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180011016`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011025`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011025`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001101c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001101c`
- `msvcrt!_vsnwprintf` at `0x1800110b9`
- `msvcrt!_vsnwprintf` at `0x1800110b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011080`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011080`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800110f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001108b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001108b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall _TraceString(int a1, char a2, __int64 a3, int a4, __int64 a5, int a6, wchar_t *Format, va_list Args)
{
  unsigned int v12; // eax
  void *v13; // rbx
  SIZE_T v14; // rsi
  _WORD *v15; // rax
  unsigned __int64 v16; // rdi
  size_t v17; // rdi
  int v18; // eax
  int v19; // ecx
  void **v20; // [rsp+20h] [rbp-69h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-61h] BYREF
  DWORD CurrentThreadId; // [rsp+38h] [rbp-51h]
  DWORD CurrentProcessId; // [rsp+3Ch] [rbp-4Dh]
  char v24; // [rsp+40h] [rbp-49h]
  int v25; // [rsp+48h] [rbp-41h]
  __int64 v26; // [rsp+50h] [rbp-39h]
  __int64 v27; // [rsp+58h] [rbp-31h]
  int v28; // [rsp+60h] [rbp-29h]
  unsigned int v29; // [rsp+64h] [rbp-25h]
  const wchar_t *v30; // [rsp+68h] [rbp-21h]
  __int64 v31; // [rsp+70h] [rbp-19h]
  __int64 v32; // [rsp+78h] [rbp-11h]

  GetLocalTime(&SystemTime);
  CurrentThreadId = GetCurrentThreadId();
  CurrentProcessId = GetCurrentProcessId();
  v24 = a2;
  v20 = &CStringTraceEvent::`vftable';
  v25 = a1;
  v26 = a3;
  v27 = a5;
  v28 = a4;
  v31 = 0;
  v32 = 0;
  v12 = a6;
  if ( a6 > 0 )
    v12 = (unsigned __int16)a6 | 0x80070000;
  v29 = v12;
  v30 = 0;
  v13 = 0;
  v14 = 128;
  while ( 1 )
  {
    v14 *= 2LL;
    LocalFree(v13);
    v15 = LocalAlloc(0, v14);
    v13 = v15;
    if ( !v15 )
      break;
    v16 = v14 >> 1;
    if ( !(v14 >> 1) )
      goto LABEL_16;
    if ( v16 > 0x7FFFFFFF )
    {
      *v15 = 0;
LABEL_16:
      LocalFree(v15);
      break;
    }
    v17 = v16 - 1;
    v18 = _vsnwprintf(v15, v17, Format, Args);
    if ( v18 < 0 || v18 > v17 )
    {
      v19 = -2147024774;
LABEL_12:
      *((_WORD *)v13 + v17) = 0;
      goto LABEL_13;
    }
    v19 = 0;
    if ( v18 == v17 )
      goto LABEL_12;
LABEL_13:
    if ( v19 != -2147024774 )
    {
      v30 = (const wchar_t *)v13;
      goto LABEL_18;
    }
  }
  v30 = L"[[Unable to format message]]";
LABEL_18:
  TraceGenericEvent((struct CTraceEvent *)&v20);
  CStringTraceEvent::~CStringTraceEvent((CStringTraceEvent *)&v20);
}

```

## disassembly

```asm
0x180010fd0  push    rbp
0x180010fd2  push    rbx
0x180010fd3  push    rsi
0x180010fd4  push    rdi
0x180010fd5  push    r12
0x180010fd7  push    r14
0x180010fd9  push    r15
0x180010fdb  lea     rbp, [rsp-7]
0x180010fe0  sub     rsp, 90h
0x180010fe7  mov     rax, cs:__security_cookie
0x180010fee  xor     rax, rsp
0x180010ff1  mov     [rbp+37h+var_40], rax
0x180010ff5  mov     r14d, r9d
0x180010ff8  mov     rsi, r8
0x180010ffb  mov     bl, dl
0x180010ffd  mov     edi, ecx
0x180010fff  mov     r15, [rbp+37h+Format]
0x180011003  mov     r12, [rbp+37h+Args]
0x180011007  lea     rax, ??_7CTraceEvent@@6B@; const CTraceEvent::`vftable'
0x18001100e  mov     [rbp+37h+var_A0], rax
0x180011012  lea     rcx, [rbp+37h+SystemTime]; lpSystemTime
0x180011016  call    cs:__imp_GetLocalTime
0x18001101c  call    cs:__imp_GetCurrentThreadId
0x180011022  mov     [rbp+37h+var_88], eax
0x180011025  call    cs:__imp_GetCurrentProcessId
0x18001102b  mov     [rbp+37h+var_84], eax
0x18001102e  mov     [rbp+37h+var_80], bl
0x180011031  lea     rax, ??_7CStringTraceEvent@@6B@; const CStringTraceEvent::`vftable'
0x180011038  mov     [rbp+37h+var_A0], rax
0x18001103c  mov     [rbp+37h+var_78], edi
0x18001103f  mov     [rbp+37h+var_70], rsi
0x180011043  mov     rax, [rbp+37h+arg_20]
0x180011047  mov     [rbp+37h+var_68], rax
0x18001104b  mov     [rbp+37h+var_60], r14d
0x18001104f  xor     r14d, r14d
0x180011052  mov     [rbp+37h+var_50], r14
0x180011056  mov     [rbp+37h+var_48], r14
0x18001105a  mov     eax, [rbp+37h+arg_28]
0x18001105d  test    eax, eax
0x18001105f  js      short loc_18001106B
0x180011061  jle     short loc_18001106B
0x180011063  movzx   eax, ax
0x180011066  or      eax, 80070000h
0x18001106b  mov     [rbp+37h+var_5C], eax
0x18001106e  mov     [rbp+37h+var_58], r14
0x180011072  mov     rbx, r14
0x180011075  mov     esi, 80h
0x18001107a  add     rsi, rsi
0x18001107d  mov     rcx, rbx; hMem
0x180011080  call    cs:__imp_LocalFree
0x180011086  mov     rdx, rsi; uBytes
0x180011089  xor     ecx, ecx; uFlags
0x18001108b  call    cs:__imp_LocalAlloc
0x180011091  mov     rbx, rax
0x180011094  test    rax, rax
0x180011097  jz      short loc_1800110FA
0x180011099  mov     rdi, rsi
0x18001109c  shr     rdi, 1
0x18001109f  jz      short loc_1800110F1
0x1800110a1  cmp     rdi, 7FFFFFFFh
0x1800110a8  ja      short loc_1800110ED
0x1800110aa  dec     rdi
0x1800110ad  mov     r9, r12; Args
0x1800110b0  mov     r8, r15; Format
0x1800110b3  mov     rdx, rdi; BufferCount
0x1800110b6  mov     rcx, rax; Buffer
0x1800110b9  call    cs:__imp__vsnwprintf
0x1800110bf  test    eax, eax
0x1800110c1  js      short loc_1800110D1
0x1800110c3  cdqe
0x1800110c5  cmp     rax, rdi
0x1800110c8  ja      short loc_1800110D1
0x1800110ca  mov     ecx, r14d
0x1800110cd  jnz     short loc_1800110DB
0x1800110cf  jmp     short loc_1800110D6
0x1800110d1  mov     ecx, 8007007Ah
0x1800110d6  mov     [rbx+rdi*2], r14w
0x1800110db  cmp     ecx, 8007007Ah
0x1800110e1  jz      short loc_18001107A
0x1800110e3  test    ecx, ecx
0x1800110e5  js      short loc_1800110F1
0x1800110e7  mov     [rbp+37h+var_58], rbx
0x1800110eb  jmp     short loc_180011105
0x1800110ed  mov     [rax], r14w
0x1800110f1  mov     rcx, rbx; hMem
0x1800110f4  call    cs:__imp_LocalFree
0x1800110fa  lea     rax, aUnableToFormat; "[[Unable to format message]]"
0x180011101  mov     [rbp+37h+var_58], rax
0x180011105  lea     rcx, [rbp+37h+var_A0]; struct CTraceEvent *
0x180011109  call    ?TraceGenericEvent@@YAXAEAVCTraceEvent@@@Z; TraceGenericEvent(CTraceEvent &)
0x18001110e  nop
0x18001110f  lea     rcx, [rbp+37h+var_A0]; this
0x180011113  call    ??1CStringTraceEvent@@UEAA@XZ; CStringTraceEvent::~CStringTraceEvent(void)
0x180011118  mov     rcx, [rbp+37h+var_40]
0x18001111c  xor     rcx, rsp; StackCookie
0x18001111f  call    __security_check_cookie
0x180011124  add     rsp, 90h
0x18001112b  pop     r15
0x18001112d  pop     r14
0x18001112f  pop     r12
0x180011131  pop     rdi
0x180011132  pop     rsi
0x180011133  pop     rbx
0x180011134  pop     rbp
0x180011135  retn
```
