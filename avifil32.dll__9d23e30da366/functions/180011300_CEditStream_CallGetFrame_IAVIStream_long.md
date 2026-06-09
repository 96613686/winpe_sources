# CEditStream::CallGetFrame(IAVIStream *,long)

- ea: `0x180011300`
- end: `0x1800113e5`
- name: `?CallGetFrame@CEditStream@@AEAAPEAUtagBITMAPINFOHEADER@@PEAUIAVIStream@@J@Z`
- size: `229`
- prototype: `struct tagBITMAPINFOHEADER *(CEditStream *__hidden this, struct IAVIStream *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180012224`
- `0x180012a44`
- `0x180012c74`

## callees

- `0x180011300`
- `0x180014350`
- `0x180018010`

## pseudocode

```c
struct tagBITMAPINFOHEADER *__fastcall CEditStream::CallGetFrame(
        CEditStream *this,
        struct IAVIStream *a2,
        unsigned int a3)
{
  PGETFRAME FrameOpen; // rax
  PGETFRAME v7; // rdi
  struct tagBITMAPINFOHEADER *result; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx

  if ( *((struct IAVIStream **)this + 31) != a2 )
  {
    FrameOpen = AVIStreamGetFrameOpen(a2, 0);
    v7 = FrameOpen;
    if ( !FrameOpen )
      return 0;
    if ( *((_QWORD *)this + 30) )
    {
      if ( ((unsigned int (__fastcall *)(PGETFRAME, _QWORD, _QWORD, _QWORD, _DWORD, int, int))FrameOpen->lpVtbl->SetFormat)(
             FrameOpen,
             *((_QWORD *)this + 32),
             0,
             0,
             0,
             -1,
             -1) )
      {
        ((void (__fastcall *)(PGETFRAME))v7->lpVtbl->Release)(v7);
        return 0;
      }
      v9 = *((_QWORD *)this + 30);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    *((_QWORD *)this + 30) = v7;
    *((_QWORD *)this + 31) = a2;
  }
  v10 = *((_QWORD *)this + 30);
  if ( v10 )
    result = (struct tagBITMAPINFOHEADER *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v10 + 24LL))(v10, a3);
  else
    result = 0;
  *((_QWORD *)this + 32) = result;
  if ( result )
    *((_DWORD *)this + 13) = result->biSizeImage;
  return result;
}

```

## disassembly

```asm
0x180011300  push    rbx
0x180011302  push    rbp
0x180011303  push    rsi
0x180011304  push    rdi
0x180011305  sub     rsp, 48h
0x180011309  mov     ebp, r8d
0x18001130c  mov     rsi, rdx
0x18001130f  mov     rbx, rcx
0x180011312  cmp     [rcx+0F8h], rdx
0x180011319  jz      loc_1800113AC
0x18001131f  xor     edx, edx; lpbiWanted
0x180011321  mov     rcx, rsi; pavi
0x180011324  call    AVIStreamGetFrameOpen
0x180011329  mov     rdi, rax
0x18001132c  test    rax, rax
0x18001132f  jnz     short loc_180011338
0x180011331  xor     eax, eax
0x180011333  jmp     loc_1800113DC
0x180011338  cmp     qword ptr [rbx+0F0h], 0
0x180011340  jz      short loc_18001139E
0x180011342  mov     rax, [rax]
0x180011345  or      ecx, 0FFFFFFFFh
0x180011348  mov     rdx, [rbx+100h]
0x18001134f  xor     r9d, r9d
0x180011352  mov     [rsp+68h+var_38], ecx
0x180011356  xor     r8d, r8d
0x180011359  mov     [rsp+68h+var_40], ecx
0x18001135d  mov     rcx, rdi
0x180011360  mov     rax, [rax+30h]
0x180011364  mov     [rsp+68h+var_48], 0
0x18001136c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011371  test    eax, eax
0x180011373  jz      short loc_180011386
0x180011375  mov     rax, [rdi]
0x180011378  mov     rcx, rdi
0x18001137b  mov     rax, [rax+10h]
0x18001137f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011384  jmp     short loc_180011331
0x180011386  mov     rcx, [rbx+0F0h]
0x18001138d  test    rcx, rcx
0x180011390  jz      short loc_18001139E
0x180011392  mov     rax, [rcx]
0x180011395  mov     rax, [rax+10h]
0x180011399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001139e  mov     [rbx+0F0h], rdi
0x1800113a5  mov     [rbx+0F8h], rsi
0x1800113ac  mov     rcx, [rbx+0F0h]
0x1800113b3  test    rcx, rcx
0x1800113b6  jnz     short loc_1800113BC
0x1800113b8  xor     eax, eax
0x1800113ba  jmp     short loc_1800113CA
0x1800113bc  mov     rax, [rcx]
0x1800113bf  mov     edx, ebp
0x1800113c1  mov     rax, [rax+18h]
0x1800113c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ca  mov     [rbx+100h], rax
0x1800113d1  test    rax, rax
0x1800113d4  jz      short loc_1800113DC
0x1800113d6  mov     ecx, [rax+14h]
0x1800113d9  mov     [rbx+34h], ecx
0x1800113dc  add     rsp, 48h
0x1800113e0  pop     rdi
0x1800113e1  pop     rsi
0x1800113e2  pop     rbp
0x1800113e3  pop     rbx
0x1800113e4  retn
```
