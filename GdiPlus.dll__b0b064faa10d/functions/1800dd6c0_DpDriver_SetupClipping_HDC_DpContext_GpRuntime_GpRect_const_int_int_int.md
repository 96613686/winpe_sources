# DpDriver::SetupClipping(HDC__ *,DpContext *,GpRuntime::GpRect const *,int &,int &,int)

- ea: `0x1800dd6c0`
- end: `0x1800dd804`
- name: `?SetupClipping@DpDriver@@UEAAXPEAUHDC__@@PEAVDpContext@@PEBVGpRect@GpRuntime@@AEAH3H@Z`
- size: `324`
- prototype: `void(DpDriver *__hidden this, HDC, struct DpContext *, const struct GpRuntime::GpRect *, int *, int *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800dd4e0`

## callees

- `0x18001d770`
- `0x180029474`
- `0x1800dd6c0`
- `0x18013da6c`

## import_xrefs

- `GDI32!ExtSelectClipRgn` at `0x1800dd7ed`
- `GDI32!ExtSelectClipRgn` at `0x1800dd7ed`
- `GDI32!IntersectClipRect` at `0x1800dd759`
- `GDI32!IntersectClipRect` at `0x1800dd759`
- `GDI32!SaveDC` at `0x1800dd73b`
- `GDI32!SaveDC` at `0x1800dd7d9`
- `GDI32!SaveDC` at `0x1800dd73b`
- `GDI32!SaveDC` at `0x1800dd7d9`
- `GDI32!DeleteObject` at `0x1800dd7f6`
- `GDI32!DeleteObject` at `0x1800dd7f6`

## pseudocode

```c
void __fastcall DpDriver::SetupClipping(
        DpDriver *this,
        HDC a2,
        struct DpContext *a3,
        const struct GpRuntime::GpRect *a4,
        int *a5,
        int *a6,
        int a7)
{
  DpRegion *v7; // rbx
  int v10; // r12d
  int v11; // ebp
  int v12; // r14d
  int v13; // r15d
  int bottom; // r12d
  HRGN HRgn; // rdi

  v7 = (struct DpContext *)((char *)a3 + 304);
  v10 = *a6;
  *a6 = 0;
  *a5 = 0;
  if ( a7
    || (unsigned int)DpRegion::GetRectVisibility(
                       v7,
                       *(unsigned int *)a4,
                       *((unsigned int *)a4 + 1),
                       (unsigned int)(*(_DWORD *)a4 + *((_DWORD *)a4 + 2)),
                       *((_DWORD *)a4 + 1) + *((_DWORD *)a4 + 3),
                       0) != 3 )
  {
    if ( *((_QWORD *)v7 + 3) )
    {
      if ( v10 && (unsigned int)SetupPathClipping(a2) )
      {
        *a5 = 1;
        *a6 = 1;
      }
      else
      {
        HRgn = (HRGN)DpRegion::GetHRgn(v7);
        if ( HRgn )
        {
          SaveDC(a2);
          ExtSelectClipRgn(a2, HRgn, 1);
          DeleteObject(HRgn);
          *a5 = 1;
        }
      }
    }
    else
    {
      *a5 = 1;
      v11 = *((_DWORD *)a3 + 78);
      v12 = *((_DWORD *)a3 + 79);
      v13 = *((_DWORD *)a3 + 80);
      bottom = *((_DWORD *)a3 + 81);
      SaveDC(a2);
      if ( (*((_BYTE *)a3 + 308) & 1) == 0 )
        IntersectClipRect(a2, v11, v12, v13, bottom);
    }
  }
}

```

## disassembly

```asm
0x1800dd6c0  push    rbx
0x1800dd6c2  push    rbp
0x1800dd6c3  push    rsi
0x1800dd6c4  push    rdi
0x1800dd6c5  push    r12
0x1800dd6c7  push    r14
0x1800dd6c9  push    r15
0x1800dd6cb  sub     rsp, 30h
0x1800dd6cf  cmp     [rsp+68h+arg_30], 0
0x1800dd6d7  lea     rbx, [r8+130h]
0x1800dd6de  mov     r15, [rsp+68h+arg_28]
0x1800dd6e6  mov     rbp, r9
0x1800dd6e9  mov     r14, [rsp+68h+arg_20]
0x1800dd6f1  mov     rdi, r8
0x1800dd6f4  mov     rsi, rdx
0x1800dd6f7  mov     r12d, [r15]
0x1800dd6fa  mov     dword ptr [r15], 0
0x1800dd701  mov     dword ptr [r14], 0
0x1800dd708  jz      short loc_1800DD76E
0x1800dd70a  cmp     qword ptr [rbx+18h], 0
0x1800dd70f  jnz     loc_1800DD7A2
0x1800dd715  mov     ebx, 1
0x1800dd71a  mov     rcx, rsi; hdc
0x1800dd71d  mov     [r14], ebx
0x1800dd720  mov     ebp, [rdi+138h]
0x1800dd726  mov     r14d, [rdi+13Ch]
0x1800dd72d  mov     r15d, [rdi+140h]
0x1800dd734  mov     r12d, [rdi+144h]
0x1800dd73b  call    cs:__imp_SaveDC
0x1800dd741  test    [rdi+134h], bl
0x1800dd747  jnz     short loc_1800DD75F
0x1800dd749  mov     r9d, r15d; right
0x1800dd74c  mov     [rsp+68h+bottom], r12d; bottom
0x1800dd751  mov     r8d, r14d; top
0x1800dd754  mov     edx, ebp; left
0x1800dd756  mov     rcx, rsi; hdc
0x1800dd759  call    cs:__imp_IntersectClipRect
0x1800dd75f  add     rsp, 30h
0x1800dd763  pop     r15
0x1800dd765  pop     r14
0x1800dd767  pop     r12
0x1800dd769  pop     rdi
0x1800dd76a  pop     rsi
0x1800dd76b  pop     rbp
0x1800dd76c  pop     rbx
0x1800dd76d  retn
0x1800dd76e  mov     ecx, [r9+0Ch]
0x1800dd772  mov     r8d, [r9+4]
0x1800dd776  add     ecx, r8d
0x1800dd779  mov     edx, [r9]
0x1800dd77c  mov     r9d, [r9+8]
0x1800dd780  mov     [rsp+68h+var_40], 0
0x1800dd789  add     r9d, edx
0x1800dd78c  mov     [rsp+68h+bottom], ecx
0x1800dd790  mov     rcx, rbx
0x1800dd793  call    ?GetRectVisibility@DpRegion@@QEAA?AW4Visibility@1@HHHHPEAVGpRect@GpRuntime@@@Z; DpRegion::GetRectVisibility(int,int,int,int,GpRuntime::GpRect *)
0x1800dd798  cmp     eax, 3
0x1800dd79b  jz      short loc_1800DD75F
0x1800dd79d  jmp     loc_1800DD70A
0x1800dd7a2  test    r12d, r12d
0x1800dd7a5  jz      short loc_1800DD7C6
0x1800dd7a7  mov     r9, rbp
0x1800dd7aa  mov     rdx, rdi
0x1800dd7ad  mov     rcx, rsi; HDC
0x1800dd7b0  call    SetupPathClipping
0x1800dd7b5  test    eax, eax
0x1800dd7b7  jz      short loc_1800DD7C6
0x1800dd7b9  mov     ebx, 1
0x1800dd7be  mov     [r14], ebx
0x1800dd7c1  mov     [r15], ebx
0x1800dd7c4  jmp     short loc_1800DD75F
0x1800dd7c6  mov     rcx, rbx; this
0x1800dd7c9  call    ?GetHRgn@DpRegion@@QEBAPEAUHRGN__@@XZ; DpRegion::GetHRgn(void)
0x1800dd7ce  mov     rdi, rax
0x1800dd7d1  test    rax, rax
0x1800dd7d4  jz      short loc_1800DD75F
0x1800dd7d6  mov     rcx, rsi; hdc
0x1800dd7d9  call    cs:__imp_SaveDC
0x1800dd7df  mov     ebx, 1
0x1800dd7e4  mov     rdx, rdi; hrgn
0x1800dd7e7  mov     r8d, ebx; mode
0x1800dd7ea  mov     rcx, rsi; hdc
0x1800dd7ed  call    cs:__imp_ExtSelectClipRgn
0x1800dd7f3  mov     rcx, rdi; ho
0x1800dd7f6  call    cs:__imp_DeleteObject
0x1800dd7fc  mov     [r14], ebx
0x1800dd7ff  jmp     loc_1800DD75F
```
