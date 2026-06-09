# CEditStream::NewEditStream(IAVIStream *)

- ea: `0x180011f9c`
- end: `0x1800120b3`
- name: `?NewEditStream@CEditStream@@SAPEAV1@PEAUIAVIStream@@@Z`
- size: `279`
- prototype: `struct CEditStream *__fastcall(struct IAVIStream *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180011404`
- `0x180011594`
- `0x180013080`

## callees

- `0x180001008`
- `0x180001048`
- `0x180011f9c`
- `0x180018010`

## pseudocode

```c
struct CEditStream *__fastcall CEditStream::NewEditStream(struct IAVIStream *a1)
{
  _QWORD *v2; // rax
  void *v3; // rbx
  char *v4; // rcx

  v2 = operator new(0x138u);
  v3 = v2;
  if ( !v2 )
    return 0;
  *v2 = &CEditStream::`vbtable';
  v2[38] = &ICEditStreamInternal::`vftable';
  v2[34] = &CEditStream::`vftable'{for `IAVIStream'};
  v2[36] = &CEditStream::`vftable'{for `IAVIEditStream'};
  *(_QWORD *)((char *)v2 + *(int *)(*v2 + 12LL)) = &CEditStream::`vftable'{for `ICEditStreamInternal'};
  *(_DWORD *)((char *)v2 + *(int *)(*v2 + 4LL) - 4) = *(_DWORD *)(*v2 + 4LL) - 272;
  *(_DWORD *)((char *)v2 + *(int *)(*v2 + 8LL) - 4) = *(_DWORD *)(*v2 + 8LL) - 288;
  *(_DWORD *)((char *)v2 + *(int *)(*v2 + 12LL) - 4) = *(_DWORD *)(*v2 + 12LL) - 304;
  v2[27] = 0;
  v2[29] = 0;
  v2[30] = 0;
  v2[31] = 0;
  *((_DWORD *)v2 + 56) = 0;
  v4 = (char *)v2 + *(int *)(*v2 + 4LL);
  if ( (*(int (__fastcall **)(char *, struct IAVIStream *, _QWORD))(*(_QWORD *)v4 + 24LL))(v4, a1, 0) < 0 )
  {
    operator delete(v3);
    return 0;
  }
  return (struct CEditStream *)v3;
}

```

## disassembly

```asm
0x180011f9c  mov     [rsp+arg_0], rbx
0x180011fa1  push    rdi
0x180011fa2  sub     rsp, 20h
0x180011fa6  mov     rdi, rcx
0x180011fa9  mov     ecx, 138h; Size
0x180011fae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011fb3  mov     rbx, rax
0x180011fb6  test    rax, rax
0x180011fb9  jz      loc_1800120A3
0x180011fbf  lea     rax, ??_8CEditStream@@7B@; const CEditStream::`vbtable'
0x180011fc6  xor     r8d, r8d
0x180011fc9  mov     [rbx], rax
0x180011fcc  lea     rcx, ??_7CEditStream@@6BIAVIEditStream@@@; const CEditStream::`vftable'{for `IAVIEditStream'}
0x180011fd3  lea     rax, ??_7ICEditStreamInternal@@6B@; const ICEditStreamInternal::`vftable'
0x180011fda  mov     [rbx+130h], rax
0x180011fe1  lea     rax, ??_7CEditStream@@6BIAVIStream@@@; const CEditStream::`vftable'{for `IAVIStream'}
0x180011fe8  mov     [rbx+110h], rax
0x180011fef  movsxd  rax, cs:dword_18001A56C
0x180011ff6  mov     [rax+rbx], rcx
0x180011ffa  mov     rax, [rbx]
0x180011ffd  movsxd  rcx, dword ptr [rax+0Ch]
0x180012001  lea     rax, ??_7CEditStream@@6BICEditStreamInternal@@@; const CEditStream::`vftable'{for `ICEditStreamInternal'}
0x180012008  mov     [rcx+rbx], rax
0x18001200c  mov     rax, [rbx]
0x18001200f  movsxd  rcx, dword ptr [rax+4]
0x180012013  lea     edx, [rcx-110h]
0x180012019  mov     [rcx+rbx-4], edx
0x18001201d  mov     rax, [rbx]
0x180012020  movsxd  rcx, dword ptr [rax+8]
0x180012024  lea     edx, [rcx-120h]
0x18001202a  mov     [rcx+rbx-4], edx
0x18001202e  mov     rax, [rbx]
0x180012031  movsxd  rcx, dword ptr [rax+0Ch]
0x180012035  lea     edx, [rcx-130h]
0x18001203b  mov     [rcx+rbx-4], edx
0x18001203f  mov     rdx, rdi
0x180012042  mov     qword ptr [rbx+0D8h], 0
0x18001204d  mov     qword ptr [rbx+0E8h], 0
0x180012058  mov     qword ptr [rbx+0F0h], 0
0x180012063  mov     qword ptr [rbx+0F8h], 0
0x18001206e  mov     dword ptr [rbx+0E0h], 0
0x180012078  mov     rax, [rbx]
0x18001207b  movsxd  rcx, dword ptr [rax+4]
0x18001207f  add     rcx, rbx
0x180012082  mov     rax, [rcx]
0x180012085  mov     rax, [rax+18h]
0x180012089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001208e  test    eax, eax
0x180012090  jns     short loc_1800120A5
0x180012092  mov     edx, 138h; unsigned __int64
0x180012097  mov     rcx, rbx; void *
0x18001209a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001209f  xor     eax, eax
0x1800120a1  jmp     short loc_1800120A8
0x1800120a3  xor     ebx, ebx
0x1800120a5  mov     rax, rbx
0x1800120a8  mov     rbx, [rsp+28h+arg_0]
0x1800120ad  add     rsp, 20h
0x1800120b1  pop     rdi
0x1800120b2  retn
```
