# CInkStrokeDisp::get_DrawingAttributes(IInkDrawingAttributes * *)

- ea: `0x180008200`
- end: `0x1800085d1`
- name: `?get_DrawingAttributes@CInkStrokeDisp@@UEAAJPEAPEAUIInkDrawingAttributes@@@Z`
- size: `977`
- prototype: `__int64 __fastcall(CInkStrokeDisp *__hidden this, struct IInkDrawingAttributes **)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x180006cc8`
- `0x180008200`
- `0x1800085d8`
- `0x180009990`
- `0x180012770`
- `0x180012ad0`
- `0x18001a200`
- `0x180022804`
- `0x180026fcc`
- `0x18004451c`
- `0x1800445e8`
- `0x180044658`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800083a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800085c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800083a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800085c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000830c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008442`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000830c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008442`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800084eb`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000854d`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1800084eb`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18000854d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180008253`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180008253`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInkStrokeDisp::get_DrawingAttributes(CInkStrokeDisp *this, struct IInkDrawingAttributes **a2)
{
  HANDLE *v4; // r8
  HANDLE *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  int DrawingAttributes; // ebx
  _DWORD *v10; // r12
  LPVOID v11; // rax
  __int64 v12; // r12
  char *v13; // rdx
  CRefCountedObject *v14; // rcx
  int v16; // r15d
  __int64 v17; // rax
  __int64 v18; // r14
  bool v19; // sf
  __int64 v20; // r15
  __int64 v21; // rcx
  volatile signed __int32 *v22; // rax
  CRefCountedObject *v23; // r15
  __int64 v24; // rcx
  __int64 v25; // [rsp+70h] [rbp+8h] BYREF
  HANDLE *v26; // [rsp+80h] [rbp+18h]
  HANDLE *v27; // [rsp+88h] [rbp+20h]

  v4 = (HANDLE *)((char *)this + 24);
  if ( this == (CInkStrokeDisp *)8 )
    v4 = 0;
  v27 = v4;
  LODWORD(v25) = 0;
  v5 = v4 + 1;
  v26 = v4 + 1;
  CoWaitForMultipleHandles(0, 0xFFFFFFFF, 1u, v4 + 1, (LPDWORD)&v25);
  if ( !a2 )
  {
    ReleaseMutex(*v5);
    return 2147500035LL;
  }
  try
  {
    *a2 = 0;
    v6 = *((_QWORD *)this + 6);
    if ( !v6
      || (v7 = *(_QWORD *)(v6 + 24)) == 0
      || !*(_QWORD *)(v7 + 112)
      || (v8 = *(_QWORD *)(v6 + 16)) == 0
      || !*(_QWORD *)(v8 + 16) )
    {
      DrawingAttributes = -2147418113;
      goto LABEL_53;
    }
    if ( *((_QWORD *)this + 8) )
      goto LABEL_21;
    v25 = 0;
    DrawingAttributes = InkStroke_GetDrawingAttributes(*(_QWORD *)(v8 + 16), &v25);
    if ( DrawingAttributes >= 0 )
    {
      v10 = (_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL);
      if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *v10 )
      {
        Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
        if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
        {
          `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
          dwFlags = 0;
          `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
          atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
          Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
        }
      }
      if ( !`WinHeap::GetDefault'::`2'::s_WinHeap
        || (v11 = HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, 0x60u)) == 0 )
      {
        DrawingAttributes = -2147024882;
        goto LABEL_53;
      }
      DrawingAttributes = -2147024882;
      v16 = -2147024882;
      v17 = ATL::CComObject<CDrawingAttributes>::CComObject<CDrawingAttributes>(v11);
      v18 = v17;
      if ( v17 )
      {
        CComMultiThreadMutexModel::SafeIncrementReference((int *)(v17 + 24));
        v16 = CDrawingAttributes::FinalConstruct((CDrawingAttributes *)v18);
        CComMultiThreadMutexModel::SafeDecrementReference((int *)(v18 + 24));
        v19 = v16 < 0;
        if ( !v16 )
        {
LABEL_28:
          if ( v19 )
          {
            DrawingAttributes = v16;
            goto LABEL_53;
          }
          if ( v18 )
          {
            v20 = v18 + 8;
            if ( v18 != -8 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v18 + 8);
            v21 = *((_QWORD *)this + 8);
            if ( v21 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            *((_QWORD *)this + 8) = v20;
            if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA > *v10 )
            {
              Init_thread_header(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
              if ( __TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA == -1 )
              {
                `WinHeap::GetDefault'::`2'::s_WinHeap = 0;
                dwFlags = 0;
                `WinHeap::GetDefault'::`2'::s_WinHeap = HeapCreate(0, 0x10000u, 0);
                atexit(`WinHeap::GetDefault'::`2'::`dynamic atexit destructor for 's_WinHeap'');
                Init_thread_footer(&__TSS0__1__GetDefault_WinHeap__SAAEAV2_XZ_4HA);
              }
            }
            if ( !`WinHeap::GetDefault'::`2'::s_WinHeap
              || (v22 = (volatile signed __int32 *)HeapAlloc(`WinHeap::GetDefault'::`2'::s_WinHeap, dwFlags, 0x18u),
                  (v23 = (CRefCountedObject *)v22) == 0) )
            {
              v12 = v25;
LABEL_47:
              v24 = *((_QWORD *)this + 8);
              if ( v24 )
              {
                *((_QWORD *)this + 8) = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              }
              DeleteDrawAttrs(v12);
              goto LABEL_53;
            }
            *(_QWORD *)v22 = &CRefCountedObject::`vftable';
            *((_DWORD *)v22 + 2) = 0;
            _InterlockedIncrement(v22 + 2);
            *(_QWORD *)v22 = &CDrawingAttributesHandle::`vftable';
            v12 = v25;
            *((_QWORD *)v22 + 2) = v25;
            v13 = (char *)this + 16;
            if ( this == (CInkStrokeDisp *)8 )
              v13 = 0;
            DrawingAttributes = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 8) + 48LL))(
                                  *((_QWORD *)this + 8),
                                  v13,
                                  **((_QWORD **)this + 8));
            if ( DrawingAttributes < 0 )
            {
              CRefCountedObject::ReleaseReference(v23);
              goto LABEL_47;
            }
            v14 = *(CRefCountedObject **)(v18 + 48);
            if ( v14 && *((_QWORD *)v14 + 2) )
              CRefCountedObject::ReleaseReference(v14);
            *(_QWORD *)(v18 + 48) = v23;
          }
LABEL_21:
          DrawingAttributes = (***((__int64 (__fastcall ****)(_QWORD, GUID *, struct IInkDrawingAttributes **))this + 8))(
                                *((_QWORD *)this + 8),
                                &GUID_bf519b75_0a15_4623_adc9_c00d436a8092,
                                a2);
          goto LABEL_53;
        }
        ATL::CComObject<CDrawingAttributes>::`scalar deleting destructor'((LPVOID)v18);
        v18 = 0;
      }
      v19 = v16 < 0;
      goto LABEL_28;
    }
  }
  catch ( ... )
  {
    LODWORD(v25) = ReportWispException();
    DrawingAttributes = v25;
    v5 = v26;
  }
LABEL_53:
  ReleaseMutex(*v5);
  return (unsigned int)DrawingAttributes;
}

```

## disassembly

```asm
0x180008200  mov     r11, rsp
0x180008203  push    rbx
0x180008204  push    rsi
0x180008205  push    rdi
0x180008206  push    r12
0x180008208  push    r13
0x18000820a  push    r14
0x18000820c  push    r15
0x18000820e  sub     rsp, 30h
0x180008212  mov     r13, rdx
0x180008215  mov     rsi, rcx
0x180008218  lea     r8, [rcx+18h]
0x18000821c  xor     r14d, r14d
0x18000821f  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180008223  cmovz   r8, r14
0x180008227  mov     [r11+20h], r8
0x18000822b  mov     [r11+8], r14d
0x18000822f  lea     rdi, [r8+8]
0x180008233  mov     [rsp+68h+arg_10], rdi
0x18000823b  lea     rax, [r11+8]
0x18000823f  mov     [r11-48h], rax
0x180008243  mov     r9, rdi; pHandles
0x180008246  mov     edx, 0FFFFFFFFh; dwTimeout
0x18000824b  xor     ecx, ecx; dwFlags
0x18000824d  mov     r8d, 1; cHandles
0x180008253  call    cs:__imp_CoWaitForMultipleHandles
0x180008259  nop
0x18000825a  test    r13, r13
0x18000825d  jz      loc_1800085BE
0x180008263  mov     [r13+0], r14
0x180008267  mov     rcx, [rsi+30h]
0x18000826b  test    rcx, rcx
0x18000826e  jz      loc_1800083C8
0x180008274  mov     rax, [rcx+18h]
0x180008278  test    rax, rax
0x18000827b  jz      loc_1800083C8
0x180008281  cmp     [rax+70h], r14
0x180008285  jz      loc_1800083C8
0x18000828b  mov     rax, [rcx+10h]
0x18000828f  test    rax, rax
0x180008292  jz      loc_1800083C8
0x180008298  cmp     [rax+10h], r14
0x18000829c  jz      loc_1800083C8
0x1800082a2  cmp     [rsi+40h], r14
0x1800082a6  jnz     loc_180008384
0x1800082ac  mov     [rsp+68h+arg_0], r14
0x1800082b1  lea     rdx, [rsp+68h+arg_0]
0x1800082b6  mov     rcx, [rax+10h]
0x1800082ba  call    InkStroke_GetDrawingAttributes
0x1800082bf  mov     ebx, eax
0x1800082c1  test    eax, eax
0x1800082c3  js      loc_18000839F
0x1800082c9  mov     ecx, cs:_tls_index
0x1800082cf  mov     rax, gs:58h
0x1800082d8  mov     edx, 4
0x1800082dd  mov     r12, [rax+rcx*8]
0x1800082e1  add     r12, rdx
0x1800082e4  mov     eax, [r12]
0x1800082e8  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x1800082ee  jg      loc_1800084BA
0x1800082f4  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x1800082fb  test    rcx, rcx
0x1800082fe  jz      short loc_18000831B
0x180008300  mov     r8d, 60h ; '`'; dwBytes
0x180008306  mov     edx, cs:dwFlags; dwFlags
0x18000830c  call    cs:__imp_HeapAlloc
0x180008312  test    rax, rax
0x180008315  jnz     loc_1800083CF
0x18000831b  mov     ebx, 8007000Eh
0x180008320  jmp     short loc_18000839F
0x180008322  lea     rax, ??_7CRefCountedObject@@6B@; const CRefCountedObject::`vftable'
0x180008329  mov     [r15], rax
0x18000832c  mov     dword ptr [r15+8], 0
0x180008334  lock inc dword ptr [r15+8]
0x180008339  lea     rax, ??_7CDrawingAttributesHandle@@6B@; const CDrawingAttributesHandle::`vftable'
0x180008340  mov     [r15], rax
0x180008343  mov     r12, [rsp+68h+arg_0]
0x180008348  mov     [r15+10h], r12
0x18000834c  mov     rcx, [rsi+40h]
0x180008350  mov     r8, [rcx]
0x180008353  lea     rdx, [rsi+10h]
0x180008357  xor     eax, eax
0x180008359  lea     r9, [rsi-8]
0x18000835d  test    r9, r9
0x180008360  cmovz   rdx, rax
0x180008364  mov     rax, [r8+30h]
0x180008368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000836d  mov     ebx, eax
0x18000836f  test    eax, eax
0x180008371  js      loc_180008577
0x180008377  mov     rcx, [r14+30h]; this
0x18000837b  test    rcx, rcx
0x18000837e  jnz     short loc_1800083BA
0x180008380  mov     [r14+30h], r15
0x180008384  mov     rcx, [rsi+40h]
0x180008388  mov     rax, [rcx]
0x18000838b  mov     r8, r13
0x18000838e  lea     rdx, _GUID_bf519b75_0a15_4623_adc9_c00d436a8092
0x180008395  mov     rax, [rax]
0x180008398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000839d  mov     ebx, eax
0x18000839f  mov     rcx, [rdi]; hMutex
0x1800083a2  call    cs:__imp_ReleaseMutex
0x1800083a8  mov     eax, ebx
0x1800083aa  add     rsp, 30h
0x1800083ae  pop     r15
0x1800083b0  pop     r14
0x1800083b2  pop     r13
0x1800083b4  pop     r12
0x1800083b6  pop     rdi
0x1800083b7  pop     rsi
0x1800083b8  pop     rbx
0x1800083b9  retn
0x1800083ba  cmp     qword ptr [rcx+10h], 0
0x1800083bf  jz      short loc_180008380
0x1800083c1  call    ?ReleaseReference@CRefCountedObject@@QEAAXXZ; CRefCountedObject::ReleaseReference(void)
0x1800083c6  jmp     short loc_180008380
0x1800083c8  mov     ebx, 8000FFFFh
0x1800083cd  jmp     short loc_18000839F
0x1800083cf  mov     ebx, 8007000Eh
0x1800083d4  mov     r15d, ebx
0x1800083d7  mov     rcx, rax
0x1800083da  call    ??0?$CComObject@VCDrawingAttributes@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CDrawingAttributes>::CComObject<CDrawingAttributes>(void *)
0x1800083df  mov     r14, rax
0x1800083e2  test    rax, rax
0x1800083e5  jnz     short loc_18000845E
0x1800083e7  test    r15d, r15d
0x1800083ea  js      loc_1800085A5
0x1800083f0  test    r14, r14
0x1800083f3  jz      short loc_180008384
0x1800083f5  lea     r15, [r14+8]
0x1800083f9  test    r15, r15
0x1800083fc  jz      short loc_18000840D
0x1800083fe  mov     rax, [r15]
0x180008401  mov     rcx, r15
0x180008404  mov     rax, [rax+8]
0x180008408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000840d  mov     rcx, [rsi+40h]
0x180008411  test    rcx, rcx
0x180008414  jnz     short loc_180008494
0x180008416  mov     [rsi+40h], r15
0x18000841a  mov     eax, [r12]
0x18000841e  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, eax
0x180008424  jg      loc_180008515
0x18000842a  mov     rcx, cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A; hHeap
0x180008431  test    rcx, rcx
0x180008434  jz      short loc_180008454
0x180008436  mov     r8d, 18h; dwBytes
0x18000843c  mov     edx, cs:dwFlags; dwFlags
0x180008442  call    cs:__imp_HeapAlloc
0x180008448  mov     r15, rax
0x18000844b  test    rax, rax
0x18000844e  jnz     loc_180008322
0x180008454  mov     r12, [rsp+68h+arg_0]
0x180008459  jmp     loc_18000857F
0x18000845e  lea     rcx, [rax+18h]; int *
0x180008462  call    ?SafeIncrementReference@CComMultiThreadMutexModel@@SAKPEAJ@Z; CComMultiThreadMutexModel::SafeIncrementReference(long *)
0x180008467  mov     rcx, r14; this
0x18000846a  call    ?FinalConstruct@CDrawingAttributes@@QEAAJXZ; CDrawingAttributes::FinalConstruct(void)
0x18000846f  mov     r15d, eax
0x180008472  lea     rcx, [r14+18h]; int *
0x180008476  call    ?SafeDecrementReference@CComMultiThreadMutexModel@@SAKPEAJ@Z; CComMultiThreadMutexModel::SafeDecrementReference(long *)
0x18000847b  test    r15d, r15d
0x18000847e  jz      loc_1800083EA
0x180008484  mov     rcx, r14; lpMem
0x180008487  call    ??_G?$CComObject@VCDrawingAttributes@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CDrawingAttributes>::`scalar deleting destructor'(uint)
0x18000848c  xor     r14d, r14d
0x18000848f  jmp     loc_1800083E7
0x180008494  mov     rax, [rcx]
0x180008497  mov     rax, [rax+10h]
0x18000849b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a0  jmp     loc_180008416
0x1800084a5  mov     rcx, r12
0x1800084a8  call    DeleteDrawAttrs
0x1800084ad  test    ebx, ebx
0x1800084af  jns     loc_180008384
0x1800084b5  jmp     loc_18000839F
0x1800084ba  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x1800084c1  call    _Init_thread_header
0x1800084c6  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x1800084cd  jnz     loc_1800082F4
0x1800084d3  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, r14; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800084da  mov     cs:dwFlags, r14d
0x1800084e1  xor     r8d, r8d; dwMaximumSize
0x1800084e4  mov     edx, 10000h; dwInitialSize
0x1800084e9  xor     ecx, ecx; flOptions
0x1800084eb  call    cs:__imp_HeapCreate
0x1800084f1  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x1800084f8  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x1800084ff  call    atexit
0x180008504  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18000850b  call    _Init_thread_footer
0x180008510  jmp     loc_1800082F4
0x180008515  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18000851c  call    _Init_thread_header
0x180008521  cmp     cs:?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA, 0FFFFFFFFh
0x180008528  jnz     loc_18000842A
0x18000852e  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, 0; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x180008539  mov     cs:dwFlags, 0
0x180008543  xor     r8d, r8d; dwMaximumSize
0x180008546  mov     edx, 10000h; dwInitialSize
0x18000854b  xor     ecx, ecx; flOptions
0x18000854d  call    cs:__imp_HeapCreate
0x180008553  mov     cs:?s_WinHeap@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4V2@A, rax; WinHeap `WinHeap::GetDefault(void)'::`2'::s_WinHeap
0x18000855a  lea     rcx, ??__Fs_WinHeap@?1??GetDefault@WinHeap@@SAAEAV1@XZ@YAXXZ; void (__cdecl *)()
0x180008561  call    atexit
0x180008566  lea     rcx, ?$TSS0@?1??GetDefault@WinHeap@@SAAEAV2@XZ@4HA
0x18000856d  call    _Init_thread_footer
0x180008572  jmp     loc_18000842A
0x180008577  mov     rcx, r15; this
0x18000857a  call    ?ReleaseReference@CRefCountedObject@@QEAAXXZ; CRefCountedObject::ReleaseReference(void)
0x18000857f  mov     rcx, [rsi+40h]
0x180008583  test    rcx, rcx
0x180008586  jz      loc_1800084A5
0x18000858c  mov     qword ptr [rsi+40h], 0
0x180008594  mov     rax, [rcx]
0x180008597  mov     rax, [rax+10h]
0x18000859b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085a0  jmp     loc_1800084A5
0x1800085a5  mov     ebx, r15d
0x1800085a8  jmp     loc_18000839F
0x1800085ad  mov     ebx, dword ptr [rsp+68h+arg_0]
0x1800085b1  mov     rdi, [rsp+68h+arg_10]
0x1800085b9  jmp     loc_18000839F
0x1800085be  mov     rcx, [rdi]; hMutex
0x1800085c1  call    cs:__imp_ReleaseMutex
0x1800085c7  mov     eax, 80004003h
0x1800085cc  jmp     loc_1800083AA
```
