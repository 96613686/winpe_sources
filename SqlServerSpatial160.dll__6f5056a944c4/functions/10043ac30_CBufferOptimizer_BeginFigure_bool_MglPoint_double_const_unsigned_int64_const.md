# CBufferOptimizer::BeginFigure(bool,MglPoint<double> const *,unsigned __int64 const *)

- ea: `0x10043ac30`
- end: `0x10043ae25`
- name: `?BeginFigure@CBufferOptimizer@@UEAAJ_NPEBU?$MglPoint@N@@PEB_K@Z`
- size: `501`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x100401f30`
- `0x100402040`
- `0x10043ac30`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10043acb5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10043ad23`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10043acb5`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x10043ad23`

## string_xrefs

- `0x10043aca0`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`
- `0x10043ad0d`: `sql\ntdbms\msql\sysclrtypes\spatial\libraries\dll\Allocator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBufferOptimizer::BeginFigure(__int64 a1, unsigned __int8 a2, __int64 a3, __int64 a4)
{
  CStructuredReconstructor *v8; // rax
  COutline *v9; // rdi
  CStructuredReconstructor *v10; // rax
  COutline *v11; // rax
  __int64 v12; // rcx
  __int64 result; // rax
  __int64 *v14; // rcx
  __int64 v15; // rax

  if ( *(_BYTE *)(a1 + 185) )
    return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(a1 + 120) + 32LL))(
             *(_QWORD *)(a1 + 120),
             a2,
             a3,
             a4);
  if ( !*(_DWORD *)(a1 + 128) && !*(_BYTE *)(a1 + 186) )
  {
    if ( g_SOSHost )
      v8 = (CStructuredReconstructor *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *))(*g_SOSMemObj + 120LL))(
                                         g_SOSMemObj,
                                         152,
                                         "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp");
    else
      v8 = (CStructuredReconstructor *)malloc(0x98u);
    v9 = 0;
    if ( v8 )
      v10 = CStructuredReconstructor::CStructuredReconstructor(v8, (struct IMglGeometrySink *)(a1 + 8), 0, 0);
    else
      v10 = 0;
    *(_QWORD *)(a1 + 32) = v10;
    if ( !v10 )
      return 2147942414LL;
    *((_QWORD *)v10 + 7) = a1 + 40;
    v11 = g_SOSHost
        ? (COutline *)(*(__int64 (__fastcall **)(_QWORD, __int64, const char *, __int64, __int64))(*g_SOSMemObj + 120LL))(
                        g_SOSMemObj,
                        528,
                        "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\dll\\Allocator.cpp",
                        26,
                        -2)
        : (COutline *)malloc(0x210u);
    if ( v11 )
      v9 = COutline::COutline(v11, *(struct CReconstructor **)(a1 + 32), 0, 0);
    *(_QWORD *)(a1 + 24) = v9;
    if ( !v9 )
      return 2147942414LL;
    *((_QWORD *)v9 + 63) = a1 + 40;
    *(_QWORD *)(*(_QWORD *)(a1 + 24) + 496LL) = *(_QWORD *)(a1 + 176);
    v12 = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(a1 + 120) = v12;
    result = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v12 + 24LL))(
               v12,
               1,
               *(_QWORD *)(a1 + 136));
    if ( (int)result < 0 )
      goto LABEL_26;
    if ( *(_BYTE *)(a1 + 188) )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 120) + 8LL))(
                 *(_QWORD *)(a1 + 120),
                 3,
                 *(_QWORD *)(a1 + 192));
      if ( (int)result < 0 )
        goto LABEL_26;
      *(_BYTE *)(a1 + 188) = 0;
    }
  }
  v14 = *(__int64 **)(a1 + 120);
  v15 = *v14;
  if ( !*(_BYTE *)(a1 + 187) )
  {
    result = (*(__int64 (__fastcall **)(__int64 *, __int64))(v15 + 8))(v14, 4);
    if ( (int)result >= 0 )
      return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(a1 + 120) + 32LL))(
               *(_QWORD *)(a1 + 120),
               a2,
               a3,
               a4);
LABEL_26:
    _mm_lfence();
    return result;
  }
  result = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(v15 + 8))(v14, 2, qword_10049A070);
  if ( (int)result < 0 )
    goto LABEL_26;
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(a1 + 120) + 32LL))(
           *(_QWORD *)(a1 + 120),
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x10043ac30  push    rdi
0x10043ac32  push    r14
0x10043ac34  push    r15
0x10043ac36  sub     rsp, 30h
0x10043ac3a  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x10043ac43  mov     [rsp+48h+arg_8], rbx
0x10043ac48  mov     [rsp+48h+arg_10], rbp
0x10043ac4d  mov     [rsp+48h+arg_18], rsi
0x10043ac52  mov     rbp, r9
0x10043ac55  mov     r14, r8
0x10043ac58  movzx   r15d, dl
0x10043ac5c  mov     rbx, rcx
0x10043ac5f  cmp     byte ptr [rcx+0B9h], 0
0x10043ac66  jnz     loc_10043ADF8
0x10043ac6c  cmp     dword ptr [rcx+80h], 0
0x10043ac73  jnz     loc_10043ADB6
0x10043ac79  cmp     byte ptr [rcx+0BAh], 0
0x10043ac80  jnz     loc_10043ADB6
0x10043ac86  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10043ac8e  jz      short loc_10043ACB0
0x10043ac90  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10043ac97  mov     rax, [rcx]
0x10043ac9a  mov     r9d, 1Ah
0x10043aca0  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10043aca7  lea     edx, [r9+7Eh]
0x10043acab  call    qword ptr [rax+78h]
0x10043acae  jmp     short loc_10043ACBB
0x10043acb0  mov     ecx, 98h; Size
0x10043acb5  call    cs:__imp_malloc
0x10043acbb  mov     [rsp+48h+arg_0], rax
0x10043acc0  xor     edi, edi
0x10043acc2  test    rax, rax
0x10043acc5  jz      short loc_10043ACDB
0x10043acc7  lea     rdx, [rbx+8]; struct IMglGeometrySink *
0x10043accb  xor     r9d, r9d; bool
0x10043acce  xor     r8d, r8d; bool
0x10043acd1  mov     rcx, rax; this
0x10043acd4  call    ??0CStructuredReconstructor@@QEAA@PEAUIMglGeometrySink@@_N1@Z; CStructuredReconstructor::CStructuredReconstructor(IMglGeometrySink *,bool,bool)
0x10043acd9  jmp     short loc_10043ACDE
0x10043acdb  mov     rax, rdi
0x10043acde  mov     [rbx+20h], rax
0x10043ace2  test    rax, rax
0x10043ace5  jz      loc_10043ADDE
0x10043aceb  lea     rsi, [rbx+28h]
0x10043acef  mov     [rax+38h], rsi
0x10043acf3  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x10043acfb  jz      short loc_10043AD1E
0x10043acfd  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10043ad04  mov     rax, [rcx]
0x10043ad07  mov     r9d, 1Ah
0x10043ad0d  lea     r8, aSqlNtdbmsMsqlS; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x10043ad14  mov     edx, 210h
0x10043ad19  call    qword ptr [rax+78h]
0x10043ad1c  jmp     short loc_10043AD29
0x10043ad1e  mov     ecx, 210h; Size
0x10043ad23  call    cs:__imp_malloc
0x10043ad29  mov     [rsp+48h+arg_0], rax
0x10043ad2e  test    rax, rax
0x10043ad31  jz      short loc_10043AD48
0x10043ad33  xor     r9d, r9d; bool
0x10043ad36  xor     r8d, r8d; bool
0x10043ad39  mov     rdx, [rbx+20h]; struct CReconstructor *
0x10043ad3d  mov     rcx, rax; this
0x10043ad40  call    ??0COutline@@QEAA@AEAVCReconstructor@@_N1@Z; COutline::COutline(CReconstructor &,bool,bool)
0x10043ad45  mov     rdi, rax
0x10043ad48  mov     [rbx+18h], rdi
0x10043ad4c  test    rdi, rdi
0x10043ad4f  jz      loc_10043ADDE
0x10043ad55  mov     [rdi+1F8h], rsi
0x10043ad5c  mov     rcx, [rbx+18h]
0x10043ad60  mov     rax, [rbx+0B0h]
0x10043ad67  mov     [rcx+1F0h], rax
0x10043ad6e  mov     rcx, [rbx+18h]
0x10043ad72  mov     [rbx+78h], rcx
0x10043ad76  mov     rax, [rcx]
0x10043ad79  mov     r8, [rbx+88h]
0x10043ad80  mov     edx, 1
0x10043ad85  call    qword ptr [rax+18h]
0x10043ad88  test    eax, eax
0x10043ad8a  js      short loc_10043ADD9
0x10043ad8c  cmp     byte ptr [rbx+0BCh], 0
0x10043ad93  jz      short loc_10043ADB6
0x10043ad95  mov     rcx, [rbx+78h]
0x10043ad99  mov     rax, [rcx]
0x10043ad9c  mov     r8, [rbx+0C0h]
0x10043ada3  mov     edx, 3
0x10043ada8  call    qword ptr [rax+8]
0x10043adab  test    eax, eax
0x10043adad  js      short loc_10043ADD9
0x10043adaf  mov     byte ptr [rbx+0BCh], 0
0x10043adb6  mov     rcx, [rbx+78h]
0x10043adba  mov     rax, [rcx]
0x10043adbd  cmp     byte ptr [rbx+0BBh], 0
0x10043adc4  jz      short loc_10043ADE5
0x10043adc6  mov     r8, cs:qword_10049A070
0x10043adcd  mov     edx, 2
0x10043add2  call    qword ptr [rax+8]
0x10043add5  test    eax, eax
0x10043add7  jns     short loc_10043ADF8
0x10043add9  lfence
0x10043addc  jmp     short loc_10043AE0C
0x10043adde  mov     eax, 8007000Eh
0x10043ade3  jmp     short loc_10043AE0C
0x10043ade5  xor     r8d, r8d
0x10043ade8  lea     edx, [r8+4]
0x10043adec  call    qword ptr [rax+8]
0x10043adef  test    eax, eax
0x10043adf1  jns     short loc_10043ADF8
0x10043adf3  lfence
0x10043adf6  jmp     short loc_10043AE0C
0x10043adf8  mov     rcx, [rbx+78h]
0x10043adfc  mov     rax, [rcx]
0x10043adff  mov     r9, rbp
0x10043ae02  mov     r8, r14
0x10043ae05  movzx   edx, r15b
0x10043ae09  call    qword ptr [rax+20h]
0x10043ae0c  mov     rbx, [rsp+48h+arg_8]
0x10043ae11  mov     rbp, [rsp+48h+arg_10]
0x10043ae16  mov     rsi, [rsp+48h+arg_18]
0x10043ae1b  add     rsp, 30h
0x10043ae1f  pop     r15
0x10043ae21  pop     r14
0x10043ae23  pop     rdi
0x10043ae24  retn
```
