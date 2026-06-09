# ATL::CDacl::RemoveAllAces(void)

- ea: `0x140012930`
- end: `0x14001298e`
- name: `?RemoveAllAces@CDacl@ATL@@UEAAXXZ`
- size: `94`
- prototype: `void __fastcall(ATL::CDacl *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140012930`
- `0x140012fc0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012953`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012975`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012953`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140012975`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CDacl::RemoveAllAces(ATL::CDacl *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(
      v2,
      *((_QWORD *)this + 4));
    free(*((void **)this + 3));
    *((_QWORD *)this + 3) = 0;
  }
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  free(*((void **)this + 1));
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x140012930  mov     [rsp+arg_0], rbx
0x140012935  push    rdi
0x140012936  sub     rsp, 20h
0x14001293a  mov     rbx, rcx
0x14001293d  mov     rcx, [rcx+18h]
0x140012941  test    rcx, rcx
0x140012944  jz      short loc_140012961
0x140012946  mov     rdx, [rbx+20h]
0x14001294a  call    ?CallDestructors@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@CAXPEAV?$CAutoPtr@VCAccessAce@CDacl@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::CallDestructors(ATL::CAutoPtr<ATL::CDacl::CAccessAce> *,unsigned __int64)
0x14001294f  mov     rcx, [rbx+18h]; Block
0x140012953  call    cs:__imp_free
0x140012959  mov     qword ptr [rbx+18h], 0
0x140012961  mov     qword ptr [rbx+20h], 0
0x140012969  mov     qword ptr [rbx+28h], 0
0x140012971  mov     rcx, [rbx+8]; Block
0x140012975  call    cs:__imp_free
0x14001297b  mov     qword ptr [rbx+8], 0
0x140012983  mov     rbx, [rsp+28h+arg_0]
0x140012988  add     rsp, 20h
0x14001298c  pop     rdi
0x14001298d  retn
```
