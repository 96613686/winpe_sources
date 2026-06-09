# CommonUtil::HrGetWindowsPath

- ea: `0x140003814`
- end: `0x1400038d4`
- name: `CommonUtil::HrGetWindowsPath`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003bc0`

## callees

- `0x140003814`
- `0x14000493c`
- `0x140005c40`
- `0x140024bcc`
- `0x140024c40`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrGetWindowsPath(__int64 (__fastcall *a1)(void *, _QWORD), _QWORD *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  int v7; // ebx
  _WORD *v8; // rbx
  int v9; // eax
  unsigned int LastFailure; // edi
  __int64 v11; // rax
  void *v12; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  v4 = a1(0, 0);
  v5 = v4;
  if ( !v4 )
    return HrGetLastFailure();
  v12 = 0;
  v7 = CommonUtil::MpNewBuffer<wchar_t>(&v12, v4);
  if ( v7 >= 0 )
  {
    v8 = v12;
    v9 = a1(v12, v5);
    if ( v9 == v5 - 1 )
    {
      v11 = (unsigned int)(v9 - 1);
      if ( v8[v11] == 92 )
        v8[v11] = 0;
      *a2 = v8;
      return 0;
    }
    else
    {
      LastFailure = HrGetLastFailure();
      if ( v8 )
        operator delete(v8);
      return LastFailure;
    }
  }
  else
  {
    if ( v12 )
      operator delete(v12);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x140003814  mov     [rsp+arg_8], rbx
0x140003819  mov     [rsp+arg_10], rbp
0x14000381e  push    rsi
0x14000381f  push    rdi
0x140003820  push    r14
0x140003822  sub     rsp, 20h
0x140003826  mov     rsi, rdx
0x140003829  mov     rbp, rcx
0x14000382c  xor     r14d, r14d
0x14000382f  mov     [rdx], r14
0x140003832  xor     edx, edx
0x140003834  xor     ecx, ecx
0x140003836  mov     rax, rbp
0x140003839  call    cs:__guard_dispatch_icall_fptr
0x14000383f  mov     edi, eax
0x140003841  test    eax, eax
0x140003843  jnz     short loc_14000384C
0x140003845  call    HrGetLastFailure
0x14000384a  jmp     short loc_1400038C1
0x14000384c  mov     [rsp+38h+arg_0], r14
0x140003851  mov     rdx, rdi
0x140003854  lea     rcx, [rsp+38h+arg_0]
0x140003859  call    ??$MpNewBuffer@_W@CommonUtil@@YAJPEAPEA_W_K@Z; CommonUtil::MpNewBuffer<wchar_t>(wchar_t * *,unsigned __int64)
0x14000385e  mov     ebx, eax
0x140003860  mov     ecx, eax
0x140003862  shr     ecx, 1Fh
0x140003865  test    cl, cl
0x140003867  jz      short loc_14000387C
0x140003869  mov     rcx, [rsp+38h+arg_0]; void *
0x14000386e  test    rcx, rcx
0x140003871  jz      short loc_140003878
0x140003873  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003878  mov     eax, ebx
0x14000387a  jmp     short loc_1400038C1
0x14000387c  mov     edx, edi
0x14000387e  mov     rbx, [rsp+38h+arg_0]
0x140003883  mov     rcx, rbx
0x140003886  mov     rax, rbp
0x140003889  call    cs:__guard_dispatch_icall_fptr
0x14000388f  lea     ecx, [rdi-1]
0x140003892  cmp     eax, ecx
0x140003894  jz      short loc_1400038AE
0x140003896  call    HrGetLastFailure
0x14000389b  mov     edi, eax
0x14000389d  test    rbx, rbx
0x1400038a0  jz      short loc_1400038AA
0x1400038a2  mov     rcx, rbx; void *
0x1400038a5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400038aa  mov     eax, edi
0x1400038ac  jmp     short loc_1400038C1
0x1400038ae  dec     eax
0x1400038b0  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x1400038b5  jnz     short loc_1400038BC
0x1400038b7  mov     [rbx+rax*2], r14w
0x1400038bc  mov     [rsi], rbx
0x1400038bf  xor     eax, eax
0x1400038c1  mov     rbx, [rsp+38h+arg_8]
0x1400038c6  mov     rbp, [rsp+38h+arg_10]
0x1400038cb  add     rsp, 20h
0x1400038cf  pop     r14
0x1400038d1  pop     rdi
0x1400038d2  pop     rsi
0x1400038d3  retn
```
