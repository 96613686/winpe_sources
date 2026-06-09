# WTL::CAppModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)

- ea: `0x180014660`
- end: `0x180014738`
- name: `?Init@CAppModule@WTL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@ATL@@PEAUHINSTANCE__@@PEBU_GUID@@@Z`
- size: `216`
- prototype: `__int64 __fastcall(WTL::CAppModule *__hidden this, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017c64`

## callees

- `0x18000193c`
- `0x180014660`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800146df`
- `KERNEL32!GetCurrentThreadId` at `0x1800146df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WTL::CAppModule::Init(
        WTL::CAppModule *this,
        struct ATL::_ATL_OBJMAP_ENTRY30 *a2,
        HINSTANCE a3,
        const struct _GUID *a4)
{
  GUID **v4; // rdi
  unsigned int v5; // ebx
  __int64 *v6; // rdi
  __int64 *v7; // rax
  DWORD CurrentThreadId; // eax
  _QWORD *v9; // rax

  ATL::CAtlModule::m_libid = LIBID_F12AppFrameClientLib;
  v4 = &off_18004B400;
  v5 = 0;
  if ( &off_18004B400 != (GUID **)-1LL )
  {
    qword_180050778 = (__int64)&off_18004B400;
    if ( off_18004B400 )
    {
      do
      {
        LOBYTE(this) = 1;
        ((void (__fastcall *)(WTL::CAppModule *, struct ATL::_ATL_OBJMAP_ENTRY30 *, HINSTANCE, const struct _GUID *))v4[8])(
          this,
          a2,
          a3,
          a4);
        v4 += 9;
      }
      while ( *v4 );
    }
  }
  v6 = off_18004BA20[0];
  v7 = off_18004BA28;
  while ( v6 < v7 )
  {
    if ( *v6 )
    {
      LOBYTE(this) = 1;
      (*(void (__fastcall **)(WTL::CAppModule *))(*v6 + 64))(this);
      v7 = off_18004BA28;
    }
    ++v6;
  }
  CurrentThreadId = GetCurrentThreadId();
  try
  {
    dword_180050780 = CurrentThreadId;
    qword_180050788 = 0;
    v9 = operator new(0x18u);
    *v9 = 0;
    v9[1] = 0;
    *((_DWORD *)v9 + 4) = 0;
    qword_180050788 = v9;
  }
  catch ( ... )
  {
    v5 = 0;
    v9 = qword_180050788;
  }
  if ( v9 )
    Block = 0;
  else
    return (unsigned int)-2147024882;
  return v5;
}

```

## disassembly

```asm
0x180014660  mov     [rsp+arg_0], rbx
0x180014665  push    rdi
0x180014666  sub     rsp, 20h
0x18001466a  movups  xmm0, xmmword ptr cs:LIBID_F12AppFrameClientLib.Data1
0x180014671  movdqu  xmmword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, xmm0; _GUID ATL::CAtlModule::m_libid ...
0x180014679  lea     rdi, off_18004B400
0x180014680  xor     ebx, ebx
0x180014682  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180014686  jz      short loc_1800146AC
0x180014688  mov     cs:qword_180050778, rdi
0x18001468f  cmp     cs:off_18004B400, rbx
0x180014696  jz      short loc_1800146AC
0x180014698  mov     cl, 1
0x18001469a  mov     rax, [rdi+40h]
0x18001469e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146a3  lea     rdi, [rdi+48h]
0x1800146a7  cmp     [rdi], rbx
0x1800146aa  jnz     short loc_180014698
0x1800146ac  mov     rdi, cs:off_18004BA20
0x1800146b3  mov     rax, cs:off_18004BA28
0x1800146ba  jmp     short loc_1800146DA
0x1800146bc  mov     rdx, [rdi]
0x1800146bf  test    rdx, rdx
0x1800146c2  jz      short loc_1800146D6
0x1800146c4  mov     cl, 1
0x1800146c6  mov     rax, [rdx+40h]
0x1800146ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146cf  mov     rax, cs:off_18004BA28
0x1800146d6  add     rdi, 8
0x1800146da  cmp     rdi, rax
0x1800146dd  jb      short loc_1800146BC
0x1800146df  call    cs:__imp_GetCurrentThreadId
0x1800146e5  mov     cs:dword_180050780, eax
0x1800146eb  mov     cs:qword_180050788, rbx
0x1800146f2  mov     ecx, 18h; Size
0x1800146f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800146fc  mov     [rax], rbx
0x1800146ff  mov     [rax+8], rbx
0x180014703  mov     [rax+10h], ebx
0x180014706  mov     cs:qword_180050788, rax
0x18001470d  jmp     short loc_180014718
0x18001470f  xor     ebx, ebx
0x180014711  mov     rax, cs:qword_180050788
0x180014718  test    rax, rax
0x18001471b  jnz     short loc_180014724
0x18001471d  mov     ebx, 8007000Eh
0x180014722  jmp     short loc_18001472B
0x180014724  mov     cs:Block, rbx
0x18001472b  mov     eax, ebx
0x18001472d  mov     rbx, [rsp+28h+arg_0]
0x180014732  add     rsp, 20h
0x180014736  pop     rdi
0x180014737  retn
```
