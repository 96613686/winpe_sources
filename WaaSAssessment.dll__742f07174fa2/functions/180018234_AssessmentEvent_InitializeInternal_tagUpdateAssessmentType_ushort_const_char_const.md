# AssessmentEvent::InitializeInternal(tagUpdateAssessmentType,ushort const *,char const *)

- ea: `0x180018234`
- end: `0x180018427`
- name: `?InitializeInternal@AssessmentEvent@@AEAAJW4tagUpdateAssessmentType@@PEBGPEBD@Z`
- size: `499`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800087d0`
- `0x1800088d0`
- `0x1800180e8`

## callees

- `0x180016e1c`
- `0x180016fd0`
- `0x180017ce8`
- `0x180018234`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800183f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800183fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800183f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800183fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800182e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800182e5`

## pseudocode

```c
__int64 __fastcall AssessmentEvent::InitializeInternal(__int64 a1, int a2, _WORD *a3, char *a4)
{
  _WORD *v5; // rsi
  signed int v7; // r10d
  __int64 v8; // rbp
  _WORD *v9; // rax
  __int64 v10; // rdx
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rbx
  _WORD *v13; // rax
  _WORD *v14; // rdx
  __int64 v15; // rax
  _WORD *v16; // rcx
  char *v17; // rdi
  __int64 v18; // rcx
  char *v19; // rdx
  char *v20; // rax
  TraceLoggingCorrelationVector *v21; // rax
  TraceLoggingCorrelationVector *v22; // rbx

  *(_DWORD *)(a1 + 156) = a2;
  *(_QWORD *)(a1 + 144) = 0;
  *(_DWORD *)(a1 + 152) = 0;
  v5 = a3;
  *(_QWORD *)(a1 + 164) = 0;
  *(_QWORD *)(a1 + 172) = 0;
  v7 = 0;
  *(_QWORD *)(a1 + 180) = 0;
  v8 = 2147483646;
  *(_DWORD *)(a1 + 188) = 0;
  if ( a3 )
  {
    v9 = a3;
    v10 = 0x7FFFFFFF;
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v10;
    }
    while ( v10 );
    v7 = v10 == 0 ? 0x80070057 : 0;
    v11 = (0x7FFFFFFF - v10) & -(__int64)(v10 != 0);
    if ( v10 )
    {
      v12 = v11 + 1;
      if ( v11 + 1 < v11 )
      {
        v7 = -2147024362;
      }
      else
      {
        v13 = CoTaskMemAlloc(2 * v12);
        *(_QWORD *)(a1 + 144) = v13;
        v14 = v13;
        if ( v12 )
        {
          if ( v12 <= 0x7FFFFFFF )
          {
            v15 = 2147483646;
            do
            {
              if ( !v15 )
                break;
              if ( !*v5 )
                break;
              *v14++ = *v5++;
              --v15;
              --v12;
            }
            while ( v12 );
            v16 = v14 - 1;
            if ( v12 )
              v16 = v14;
            v7 = v12 == 0 ? 0x8007007A : 0;
            *v16 = 0;
          }
          else
          {
            v7 = -2147024809;
            *v13 = 0;
          }
        }
        else
        {
          v7 = -2147024809;
        }
      }
    }
  }
  if ( !a4 )
    return (unsigned int)GenerateCorrelationVector((char *)(a1 + 8));
  if ( v7 >= 0 )
  {
    v17 = (char *)(a1 + 8);
    v18 = 129;
    v19 = v17;
    do
    {
      if ( !v8 )
        break;
      if ( !*a4 )
        break;
      *v19++ = *a4++;
      --v8;
      --v18;
    }
    while ( v18 );
    v20 = v19 - 1;
    v7 = v18 == 0 ? 0x8007007A : 0;
    if ( v18 )
      v20 = v19;
    *v20 = 0;
    if ( v18 )
    {
      if ( v17 )
      {
        v21 = TraceLoggingCorrelationVector::Extend(v17, (bool)v19);
        v22 = v21;
        if ( v21 )
        {
          if ( TraceLoggingCorrelationVector::ToString(v21, v17) )
          {
            operator delete(v22);
            return 0;
          }
          operator delete(v22);
        }
        return (unsigned int)-2147024882;
      }
      else
      {
        return (unsigned int)-2147467261;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180018234  push    rbx
0x180018236  push    rbp
0x180018237  push    rsi
0x180018238  push    rdi
0x180018239  push    r13
0x18001823b  push    r14
0x18001823d  push    r15
0x18001823f  sub     rsp, 20h
0x180018243  xor     r15d, r15d
0x180018246  mov     [rcx+9Ch], edx
0x18001824c  mov     [rcx+90h], r15
0x180018253  mov     r14, r9
0x180018256  mov     [rcx+98h], r15d
0x18001825d  mov     rsi, r8
0x180018260  mov     [rcx+0A4h], r15
0x180018267  mov     rdi, rcx
0x18001826a  mov     [rcx+0ACh], r15
0x180018271  mov     r10d, r15d
0x180018274  mov     [rcx+0B4h], r15
0x18001827b  mov     ebp, 7FFFFFFEh
0x180018280  mov     [rcx+0BCh], r15d
0x180018287  test    r8, r8
0x18001828a  jz      loc_180018363
0x180018290  lea     r13d, [rbp+1]
0x180018294  mov     rax, r8
0x180018297  mov     edx, r13d
0x18001829a  cmp     [rax], r15w
0x18001829e  jz      short loc_1800182AA
0x1800182a0  add     rax, 2
0x1800182a4  sub     rdx, 1
0x1800182a8  jnz     short loc_18001829A
0x1800182aa  mov     rax, rdx
0x1800182ad  mov     rcx, r13
0x1800182b0  neg     rax
0x1800182b3  mov     rax, rdx
0x1800182b6  sbb     r10d, r10d
0x1800182b9  sub     rcx, rdx
0x1800182bc  not     r10d
0x1800182bf  and     r10d, 80070057h
0x1800182c6  neg     rax
0x1800182c9  sbb     r8, r8
0x1800182cc  and     r8, rcx
0x1800182cf  test    rdx, rdx
0x1800182d2  jz      loc_180018363
0x1800182d8  lea     rbx, [r8+1]
0x1800182dc  cmp     rbx, r8
0x1800182df  jb      short loc_18001835D
0x1800182e1  lea     rcx, [rbx+rbx]; cb
0x1800182e5  call    cs:__imp_CoTaskMemAlloc
0x1800182eb  mov     [rdi+90h], rax
0x1800182f2  mov     rdx, rax
0x1800182f5  test    rbx, rbx
0x1800182f8  jz      short loc_18001834C
0x1800182fa  cmp     rbx, r13
0x1800182fd  jbe     short loc_180018307
0x1800182ff  mov     r10d, 80070057h
0x180018305  jmp     short loc_180018357
0x180018307  mov     rax, rbp
0x18001830a  test    rax, rax
0x18001830d  jz      short loc_18001832B
0x18001830f  movzx   ecx, word ptr [rsi]
0x180018312  test    cx, cx
0x180018315  jz      short loc_18001832B
0x180018317  mov     [rdx], cx
0x18001831a  add     rsi, 2
0x18001831e  add     rdx, 2
0x180018322  dec     rax
0x180018325  sub     rbx, 1
0x180018329  jnz     short loc_18001830A
0x18001832b  test    rbx, rbx
0x18001832e  lea     rcx, [rdx-2]
0x180018332  cmovnz  rcx, rdx
0x180018336  neg     rbx
0x180018339  sbb     r10d, r10d
0x18001833c  not     r10d
0x18001833f  and     r10d, 8007007Ah
0x180018346  mov     [rcx], r15w
0x18001834a  jmp     short loc_180018363
0x18001834c  mov     r10d, 80070057h
0x180018352  test    rbx, rbx
0x180018355  jz      short loc_180018363
0x180018357  mov     [rax], r15w
0x18001835b  jmp     short loc_180018363
0x18001835d  mov     r10d, 80070216h
0x180018363  test    r14, r14
0x180018366  jz      loc_180018409
0x18001836c  test    r10d, r10d
0x18001836f  js      loc_180018415
0x180018375  add     rdi, 8
0x180018379  mov     ecx, 81h
0x18001837e  mov     rdx, rdi
0x180018381  test    rbp, rbp
0x180018384  jz      short loc_18001839E
0x180018386  mov     al, [r14]
0x180018389  test    al, al
0x18001838b  jz      short loc_18001839E
0x18001838d  mov     [rdx], al
0x18001838f  inc     r14
0x180018392  inc     rdx; bool
0x180018395  dec     rbp
0x180018398  sub     rcx, 1
0x18001839c  jnz     short loc_180018381
0x18001839e  mov     rax, rcx
0x1800183a1  neg     rax
0x1800183a4  lea     rax, [rdx-1]
0x1800183a8  sbb     r10d, r10d
0x1800183ab  not     r10d
0x1800183ae  and     r10d, 8007007Ah
0x1800183b5  test    rcx, rcx
0x1800183b8  cmovnz  rax, rdx
0x1800183bc  mov     [rax], r15b
0x1800183bf  jz      short loc_180018415
0x1800183c1  test    rdi, rdi
0x1800183c4  jnz     short loc_1800183CE
0x1800183c6  mov     r10d, 80004003h
0x1800183cc  jmp     short loc_180018415
0x1800183ce  mov     rcx, rdi; Source
0x1800183d1  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800183d6  mov     rbx, rax
0x1800183d9  test    rax, rax
0x1800183dc  jz      short loc_1800183F6
0x1800183de  mov     rdx, rdi; Destination
0x1800183e1  mov     rcx, rax; this
0x1800183e4  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x1800183e9  mov     rcx, rbx
0x1800183ec  test    al, al
0x1800183ee  jnz     short loc_1800183FE
0x1800183f0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800183f6  mov     r10d, 8007000Eh
0x1800183fc  jmp     short loc_180018415
0x1800183fe  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018404  mov     r10d, r15d
0x180018407  jmp     short loc_180018415
0x180018409  lea     rcx, [rdi+8]; Destination
0x18001840d  call    ?GenerateCorrelationVector@@YAJPEAD@Z; GenerateCorrelationVector(char *)
0x180018412  mov     r10d, eax
0x180018415  mov     eax, r10d
0x180018418  add     rsp, 20h
0x18001841c  pop     r15
0x18001841e  pop     r14
0x180018420  pop     r13
0x180018422  pop     rdi
0x180018423  pop     rsi
0x180018424  pop     rbp
0x180018425  pop     rbx
0x180018426  retn
```
