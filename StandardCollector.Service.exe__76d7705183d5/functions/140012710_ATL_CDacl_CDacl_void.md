# ATL::CDacl::~CDacl(void)

- ea: `0x140012710`
- end: `0x14001279f`
- name: `??1CDacl@ATL@@UEAA@XZ`
- size: `143`
- prototype: `void __fastcall(ATL::CDacl *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140011b04`
- `0x140012800`
- `0x140015a74`

## callees

- `0x140012710`
- `0x140012fc0`
- `0x140013018`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012744`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012765`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012744`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012765`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012798`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CDacl::~CDacl(ATL::CDacl *this)
{
  char *v2; // rdi
  __int64 v3; // rcx

  *(_QWORD *)this = &ATL::CDacl::`vftable';
  v2 = (char *)this + 24;
  v3 = *((_QWORD *)this + 3);
  if ( v3 )
  {
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
      v3,
      *((_QWORD *)v2 + 1));
    free(*(void **)v2);
    *(_QWORD *)v2 = 0;
  }
  *((_QWORD *)v2 + 1) = 0;
  *((_QWORD *)v2 + 2) = 0;
  free(*((void **)this + 1));
  *((_QWORD *)this + 1) = 0;
  ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(v2);
  *(_QWORD *)this = &ATL::CAcl::`vftable';
  free(*((void **)this + 1));
}

```

## disassembly

```asm
0x140012710  mov     [rsp+arg_0], rbx
0x140012715  mov     [rsp+arg_8], rsi
0x14001271a  push    rdi
0x14001271b  sub     rsp, 20h
0x14001271f  mov     rsi, rcx
0x140012722  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x140012729  mov     [rcx], rax
0x14001272c  lea     rdi, [rcx+18h]
0x140012730  mov     rcx, [rdi]
0x140012733  test    rcx, rcx
0x140012736  jz      short loc_140012751
0x140012738  mov     rdx, [rdi+8]
0x14001273c  call    ?CallDestructors@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@CAXPEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(ATL::CAutoPtr<ATL::CDacl::CAccessAce> *,unsigned __int64)
0x140012741  mov     rcx, [rdi]; Block
0x140012744  call    cs:__imp_free
0x14001274a  mov     qword ptr [rdi], 0
0x140012751  mov     qword ptr [rdi+8], 0
0x140012759  mov     qword ptr [rdi+10h], 0
0x140012761  mov     rcx, [rsi+8]; Block
0x140012765  call    cs:__imp_free
0x14001276b  mov     qword ptr [rsi+8], 0
0x140012773  mov     rcx, rdi
0x140012776  call    ??1?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::~CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>(void)
0x14001277b  lea     rax, ??_7CAcl@ATL@@6B@; const ATL::CAcl::`vftable'
0x140012782  mov     [rsi], rax
0x140012785  mov     rcx, [rsi+8]
0x140012789  mov     rbx, [rsp+28h+arg_0]
0x14001278e  mov     rsi, [rsp+28h+arg_8]
0x140012793  add     rsp, 20h
0x140012797  pop     rdi
0x140012798  jmp     cs:__imp_free
```
