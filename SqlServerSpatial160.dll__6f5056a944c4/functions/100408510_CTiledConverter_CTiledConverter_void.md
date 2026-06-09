# CTiledConverter::~CTiledConverter(void)

- ea: `0x100408510`
- end: `0x10040860a`
- name: `??1CTiledConverter@@UEAA@XZ`
- size: `250`
- prototype: `void __fastcall(CTiledConverter *__hidden this)`
- caller_count: `48`
- callee_count: `1`
- tags: ``

## callers

- `0x100408680`
- `0x1004086c0`
- `0x100408800`
- `0x1004088d0`
- `0x100408a60`
- `0x100409f40`
- `0x100409fd0`
- `0x10040a660`
- `0x10040ae90`
- `0x10040b860`
- `0x10040c960`
- `0x10040d010`
- `0x100417030`
- `0x10041b930`
- `0x100427060`
- `0x1004272b0`
- `0x100427320`
- `0x100427880`
- `0x10046c310`
- `0x10046c36c`
- `0x10046c3fb`
- `0x10046c44a`
- `0x10046c4eb`
- `0x10046c53a`
- `0x10046c652`
- `0x10046c6a1`
- `0x10046cc67`
- `0x10046ccb6`
- `0x10046cd67`
- `0x10046cdb6`
- `0x10046d0ad`
- `0x10046d0fc`
- `0x10046d529`
- `0x10046d578`
- `0x10046dad4`
- `0x10046db23`
- `0x10046e135`
- `0x10046e184`
- `0x100473291`
- `0x1004732e0`
- `0x1004733fd`
- `0x10047344c`
- `0x100474917`
- `0x100474966`
- `0x100475fa0`
- `0x100476000`
- `0x100476200`
- `0x100476356`

## callees

- `0x100408510`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x100408589`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004085cb`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100408589`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004085cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CTiledConverter::~CTiledConverter(CTiledConverter *this)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  void *v3; // rdx

  *((_QWORD *)this + 32) = &COrientationChecker::`vftable';
  v2 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 34);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = (void *)*((_QWORD *)this + 28);
  if ( g_SOSHost )
  {
    if ( v3 )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(v3);
  }
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 27) = 0;
  if ( g_SOSHost )
  {
    if ( *((_QWORD *)this + 26) )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(*((void **)this + 26));
  }
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 23) = &CTiledConverter::CBoundary::`vftable';
  *(_QWORD *)this = &CGeodeticConverter::`vftable';
  *(_QWORD *)this = &IMglGeometrySink::`vftable';
}

```

## disassembly

```asm
0x100408510  mov     [rsp+arg_0], rcx
0x100408515  push    rdi
0x100408516  sub     rsp, 30h
0x10040851a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100408523  mov     [rsp+38h+arg_10], rbx
0x100408528  mov     [rsp+38h+arg_18], rsi
0x10040852d  mov     rbx, rcx
0x100408530  lea     rax, ??_7COrientationChecker@@6B@
0x100408537  mov     [rcx+100h], rax
0x10040853e  mov     rcx, [rcx+110h]
0x100408545  test    rcx, rcx
0x100408548  jz      short loc_100408555
0x10040854a  mov     rax, [rcx]
0x10040854d  mov     edx, 1
0x100408552  call    qword ptr [rax]
0x100408554  nop
0x100408555  lea     rdi, [rbx+0D8h]
0x10040855c  mov     [rsp+38h+arg_8], rdi
0x100408561  mov     rdx, [rdi+8]
0x100408565  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0
0x10040856d  jz      short loc_100408586
0x10040856f  test    rdx, rdx
0x100408572  jz      short loc_10040858F
0x100408574  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A
0x10040857b  mov     rax, [rcx]
0x10040857e  call    qword ptr [rax+80h]
0x100408584  jmp     short loc_10040858F
0x100408586  mov     rcx, rdx; Block
0x100408589  call    cs:__imp_free
0x10040858f  xor     esi, esi
0x100408591  mov     [rdi+8], rsi
0x100408595  mov     [rdi], rsi
0x100408598  lea     rdi, [rbx+0C8h]
0x10040859f  mov     [rsp+38h+arg_8], rdi
0x1004085a4  mov     rdx, [rdi+8]
0x1004085a8  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rsi
0x1004085af  jz      short loc_1004085C8
0x1004085b1  test    rdx, rdx
0x1004085b4  jz      short loc_1004085D1
0x1004085b6  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A
0x1004085bd  mov     rax, [rcx]
0x1004085c0  call    qword ptr [rax+80h]
0x1004085c6  jmp     short loc_1004085D1
0x1004085c8  mov     rcx, rdx; Block
0x1004085cb  call    cs:__imp_free
0x1004085d1  mov     [rdi+8], rsi
0x1004085d5  mov     [rdi], rsi
0x1004085d8  lea     rax, ??_7CBoundary@CTiledConverter@@6B@
0x1004085df  mov     [rbx+0B8h], rax
0x1004085e6  lea     rax, ??_7CGeodeticConverter@@6B@
0x1004085ed  mov     [rbx], rax
0x1004085f0  lea     rax, ??_7IMglGeometrySink@@6B@
0x1004085f7  mov     [rbx], rax
0x1004085fa  mov     rbx, [rsp+38h+arg_10]
0x1004085ff  mov     rsi, [rsp+38h+arg_18]
0x100408604  add     rsp, 30h
0x100408608  pop     rdi
0x100408609  retn
```
