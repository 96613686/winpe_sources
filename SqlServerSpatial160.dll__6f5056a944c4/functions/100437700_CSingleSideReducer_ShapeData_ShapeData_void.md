# CSingleSideReducer::ShapeData::~ShapeData(void)

- ea: `0x100437700`
- end: `0x10043779b`
- name: `??1ShapeData@CSingleSideReducer@@QEAA@XZ`
- size: `155`
- prototype: `void __fastcall(CSingleSideReducer::ShapeData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x100476e1c`

## callees

- `0x100437700`
- `0x100439420`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x100437743`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10043777a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100437743`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x10043777a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSingleSideReducer::ShapeData::~ShapeData(CSingleSideReducer::ShapeData *this)
{
  void *v2; // rdx

  v2 = (void *)*((_QWORD *)this + 8);
  if ( g_SOSHost )
  {
    if ( v2 )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(v2);
  }
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 7) = 0;
  if ( g_SOSHost )
  {
    if ( *((_QWORD *)this + 6) )
      (*(void (__fastcall **)(_QWORD))(*g_SOSMemObj + 128LL))(g_SOSMemObj);
  }
  else
  {
    free(*((void **)this + 6));
  }
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 5) = 0;
  ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>((__int64)this + 16);
}

```

## disassembly

```asm
0x100437700  mov     [rsp+arg_0], rcx
0x100437705  push    rdi
0x100437706  sub     rsp, 30h
0x10043770a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x100437713  mov     [rsp+38h+arg_8], rbx
0x100437718  mov     rbx, rcx
0x10043771b  mov     rdx, [rcx+40h]
0x10043771f  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, 0; SOS_AutoHost g_SOSHost
0x100437727  jz      short loc_100437740
0x100437729  test    rdx, rdx
0x10043772c  jz      short loc_100437749
0x10043772e  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x100437735  mov     rax, [rcx]
0x100437738  call    qword ptr [rax+80h]
0x10043773e  jmp     short loc_100437749
0x100437740  mov     rcx, rdx; Block
0x100437743  call    cs:__imp_free
0x100437749  xor     edi, edi
0x10043774b  mov     [rbx+40h], rdi
0x10043774f  mov     [rbx+38h], rdi
0x100437753  mov     rdx, [rbx+30h]
0x100437757  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rdi; SOS_AutoHost g_SOSHost
0x10043775e  jz      short loc_100437777
0x100437760  test    rdx, rdx
0x100437763  jz      short loc_100437780
0x100437765  mov     rcx, cs:?g_SOSMemObj@@3VSOS_AutoMemObj@@A; SOS_AutoMemObj g_SOSMemObj
0x10043776c  mov     rax, [rcx]
0x10043776f  call    qword ptr [rax+80h]
0x100437775  jmp     short loc_100437780
0x100437777  mov     rcx, rdx; Block
0x10043777a  call    cs:__imp_free
0x100437780  mov     [rbx+30h], rdi
0x100437784  mov     [rbx+28h], rdi
0x100437788  lea     rcx, [rbx+10h]
0x10043778c  mov     rbx, [rsp+38h+arg_8]
0x100437791  add     rsp, 30h
0x100437795  pop     rdi
0x100437796  jmp     ??1?$ArrayOverPages@UShapeData@CSingleSideReducer@@V?$Default_Allocator@UShapeData@CSingleSideReducer@@@@@@QEAA@XZ; ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>::~ArrayOverPages<CSingleSideReducer::ShapeData,Default_Allocator<CSingleSideReducer::ShapeData>>(void)
```
