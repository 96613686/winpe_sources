# AppendTempFileList

- ea: `0x18000a420`
- end: `0x18000a589`
- name: `AppendTempFileList`
- size: `361`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800093f0`
- `0x18000ae00`

## callees

- `0x180001f7c`
- `0x180009240`
- `0x180009268`
- `0x180009834`
- `0x18000a420`
- `0x18001275c`
- `0x1800128f4`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18000a48f`
- `KERNEL32!InitializeCriticalSection` at `0x18000a48f`
- `KERNEL32!EnterCriticalSection` at `0x18000a4fd`
- `KERNEL32!EnterCriticalSection` at `0x18000a4fd`
- `KERNEL32!LeaveCriticalSection` at `0x18000a526`
- `KERNEL32!LeaveCriticalSection` at `0x18000a526`

## pseudocode

```c
__int64 __fastcall AppendTempFileList(void **a1, const unsigned __int16 *a2, int a3)
{
  int v6; // esi
  char *v7; // rbx
  void *v8; // r14
  __int64 v9; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  __int64 v11; // rdx
  int inserted; // ebx
  char *v14; // [rsp+50h] [rbp+30h] BYREF
  struct TEMPFILEINFO *v15; // [rsp+68h] [rbp+48h] BYREF

  v6 = -2147024809;
  if ( a1 && a2 )
  {
    v7 = (char *)*a1;
    v8 = 0;
    v14 = 0;
    if ( v7 )
    {
      v8 = v7;
      v14 = v7;
    }
    else
    {
      v6 = -2147024882;
      v7 = (char *)operator new(0x38u);
      if ( v7 )
      {
        *(_QWORD *)v7 = &TEMPFILELIST::`vftable';
        *((_QWORD *)v7 + 1) = 0;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
        v15 = (struct TEMPFILEINFO *)v7;
        v9 = OE_DPA_Create();
        *((_QWORD *)v7 + 1) = v9;
        if ( v9 )
        {
          v8 = v7;
          v14 = v7;
          v15 = 0;
          v6 = 0;
        }
        else
        {
          v7 = 0;
        }
        OE_SafeReleaseAndNullPtr<TEMPFILELIST>(&v15);
      }
      else
      {
        v7 = 0;
      }
      if ( v6 < 0 )
        goto LABEL_21;
    }
    v15 = 0;
    v6 = TEMPFILEINFO::CreateInstance(a2, a3, &v15);
    if ( v6 >= 0 )
    {
      v10 = (struct _RTL_CRITICAL_SECTION *)(v7 + 16);
      EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
      v6 = 0;
      inserted = OE_DPA_InsertPtr(*((_QWORD *)v7 + 1), v11, (__int64)v15);
      if ( inserted == -1 )
        v6 = -2147024882;
      LeaveCriticalSection(v10);
      if ( inserted != -1 )
      {
        v15 = 0;
        v6 = 0;
      }
      OE_SafeReleaseAndNullPtr<TEMPFILEINFO>(&v15);
      if ( v6 >= 0 )
      {
        if ( *a1 )
          goto LABEL_22;
        *a1 = v8;
        v14 = 0;
      }
    }
LABEL_21:
    if ( !*a1 )
    {
LABEL_23:
      OE_SafeReleaseAndNullPtr<TEMPFILELIST>(&v14);
      return (unsigned int)v6;
    }
LABEL_22:
    v14 = 0;
    goto LABEL_23;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000a420  mov     [rsp-28h+arg_8], rbx
0x18000a425  mov     [rsp-28h+arg_10], rsi
0x18000a42a  push    rbp
0x18000a42b  push    rdi
0x18000a42c  push    r12
0x18000a42e  push    r14
0x18000a430  push    r15
0x18000a432  mov     rbp, rsp
0x18000a435  sub     rsp, 20h
0x18000a439  mov     r12d, r8d
0x18000a43c  mov     rdi, rdx
0x18000a43f  mov     r15, rcx
0x18000a442  mov     esi, 80070057h
0x18000a447  test    rcx, rcx
0x18000a44a  jz      loc_18000A570
0x18000a450  test    rdx, rdx
0x18000a453  jz      loc_18000A570
0x18000a459  mov     rbx, [rcx]
0x18000a45c  xor     r14d, r14d
0x18000a45f  mov     [rbp+arg_0], r14
0x18000a463  test    rbx, rbx
0x18000a466  jnz     short loc_18000A4D2
0x18000a468  lea     ecx, [rbx+38h]; Size
0x18000a46b  mov     esi, 8007000Eh
0x18000a470  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a475  mov     rbx, rax
0x18000a478  test    rax, rax
0x18000a47b  jz      short loc_18000A4C7
0x18000a47d  lea     rax, ??_7TEMPFILELIST@@6B@; const TEMPFILELIST::`vftable'
0x18000a484  mov     [rbx], rax
0x18000a487  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a48b  mov     [rbx+8], r14
0x18000a48f  call    cs:__imp_InitializeCriticalSection
0x18000a495  mov     [rbp+arg_18], rbx
0x18000a499  call    OE_DPA_Create
0x18000a49e  mov     [rbx+8], rax
0x18000a4a2  test    rax, rax
0x18000a4a5  jnz     short loc_18000A4AB
0x18000a4a7  xor     ebx, ebx
0x18000a4a9  jmp     short loc_18000A4BC
0x18000a4ab  mov     r14, rbx
0x18000a4ae  mov     [rbp+arg_0], rbx
0x18000a4b2  mov     [rbp+arg_18], 0
0x18000a4ba  xor     esi, esi
0x18000a4bc  lea     rcx, [rbp+arg_18]
0x18000a4c0  call    ??$OE_SafeReleaseAndNullPtr@VTEMPFILELIST@@@@YAXAEAPEAVTEMPFILELIST@@@Z; OE_SafeReleaseAndNullPtr<TEMPFILELIST>(TEMPFILELIST * &)
0x18000a4c5  jmp     short loc_18000A4C9
0x18000a4c7  xor     ebx, ebx
0x18000a4c9  test    esi, esi
0x18000a4cb  jns     short loc_18000A4D9
0x18000a4cd  jmp     loc_18000A559
0x18000a4d2  mov     r14, rbx
0x18000a4d5  mov     [rbp+arg_0], rbx
0x18000a4d9  lea     r8, [rbp+arg_18]; struct TEMPFILEINFO **
0x18000a4dd  mov     [rbp+arg_18], 0
0x18000a4e5  mov     edx, r12d; int
0x18000a4e8  mov     rcx, rdi; unsigned __int16 *
0x18000a4eb  call    ?CreateInstance@TEMPFILEINFO@@SAJPEBGHPEAPEAV1@@Z; TEMPFILEINFO::CreateInstance(ushort const *,int,TEMPFILEINFO * *)
0x18000a4f0  mov     esi, eax
0x18000a4f2  test    eax, eax
0x18000a4f4  js      short loc_18000A559
0x18000a4f6  lea     rdi, [rbx+10h]
0x18000a4fa  mov     rcx, rdi; lpCriticalSection
0x18000a4fd  call    cs:__imp_EnterCriticalSection
0x18000a503  mov     r8, [rbp+arg_18]
0x18000a507  mov     rcx, [rbx+8]
0x18000a50b  call    OE_DPA_InsertPtr
0x18000a510  xor     esi, esi
0x18000a512  mov     ebx, eax
0x18000a514  or      r12d, 0FFFFFFFFh
0x18000a518  mov     rcx, rdi; lpCriticalSection
0x18000a51b  cmp     eax, r12d
0x18000a51e  mov     eax, 8007000Eh
0x18000a523  cmovz   esi, eax
0x18000a526  call    cs:__imp_LeaveCriticalSection
0x18000a52c  cmp     ebx, r12d
0x18000a52f  jz      short loc_18000A53B
0x18000a531  mov     [rbp+arg_18], 0
0x18000a539  xor     esi, esi
0x18000a53b  lea     rcx, [rbp+arg_18]
0x18000a53f  call    ??$OE_SafeReleaseAndNullPtr@VTEMPFILEINFO@@@@YAXAEAPEAVTEMPFILEINFO@@@Z; OE_SafeReleaseAndNullPtr<TEMPFILEINFO>(TEMPFILEINFO * &)
0x18000a544  test    esi, esi
0x18000a546  js      short loc_18000A559
0x18000a548  cmp     qword ptr [r15], 0
0x18000a54c  jnz     short loc_18000A55F
0x18000a54e  mov     [r15], r14
0x18000a551  mov     [rbp+arg_0], 0
0x18000a559  cmp     qword ptr [r15], 0
0x18000a55d  jz      short loc_18000A567
0x18000a55f  mov     [rbp+arg_0], 0
0x18000a567  lea     rcx, [rbp+arg_0]
0x18000a56b  call    ??$OE_SafeReleaseAndNullPtr@VTEMPFILELIST@@@@YAXAEAPEAVTEMPFILELIST@@@Z; OE_SafeReleaseAndNullPtr<TEMPFILELIST>(TEMPFILELIST * &)
0x18000a570  mov     rbx, [rsp+20h+arg_8]
0x18000a575  mov     eax, esi
0x18000a577  mov     rsi, [rsp+20h+arg_10]
0x18000a57c  add     rsp, 20h
0x18000a580  pop     r15
0x18000a582  pop     r14
0x18000a584  pop     r12
0x18000a586  pop     rdi
0x18000a587  pop     rbp
0x18000a588  retn
```
