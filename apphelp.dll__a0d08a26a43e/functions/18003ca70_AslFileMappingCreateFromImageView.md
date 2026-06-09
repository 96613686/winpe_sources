# AslFileMappingCreateFromImageView

- ea: `0x18003ca70`
- end: `0x18003cbb1`
- name: `AslFileMappingCreateFromImageView`
- size: `321`
- prototype: `__int64 __fastcall(const wchar_t ***, _WORD *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004cb90`

## callees

- `0x18000f114`
- `0x180013424`
- `0x18001577c`
- `0x180015e8c`
- `0x18003ca70`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003cacc`
- `ntdll!RtlAllocateHeap` at `0x18003cacc`

## string_xrefs

- `0x18003cb06`: `AslFileMappingCreateFromImageView`
- `0x18003cb72`: `AslFileMappingCreateFromImageView`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreateFromImageView(
        const wchar_t ***a1,
        _WORD *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  const wchar_t **Heap; // rax
  const wchar_t **v9; // rbx
  unsigned int v10; // edi
  int v11; // eax
  _DWORD *v12; // rdi
  int FileKind; // eax

  if ( !a2 || !*a2 || !a1 || !a3 )
    return 3221225485LL;
  *a1 = 0;
  Heap = (const wchar_t **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v9 = Heap;
  if ( Heap )
  {
    v11 = AslStringDuplicate(Heap, a2);
    v10 = v11;
    if ( v11 >= 0 )
    {
      *((_DWORD *)v9 + 18) = 1;
      v9[1] = 0;
      v12 = v9 + 7;
      v9[6] = (const wchar_t *)0x1000000;
      v9[2] = 0;
      v9[3] = a4;
      v9[4] = a3;
      v9[5] = a4;
      if ( a4 )
      {
        FileKind = AslpFileMappingGetFileKind(v9 + 1, v9 + 7);
        if ( FileKind < 0 )
        {
          AslLogCallPrintf(
            1,
            "AslFileMappingCreateFromImageView",
            354,
            "AslpFileMappingGetFileKind failed %S [%x]",
            *v9,
            FileKind);
          *v12 = 3;
        }
      }
      else
      {
        *v12 = 1;
      }
      *a1 = v9;
      return 0;
    }
    else
    {
      AslLogCallPrintf(1, "AslFileMappingCreateFromImageView", 321, "AslStringDuplicate failed [%x]", v11);
      AslFileMappingDelete(v9);
    }
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v10;
}

```

## disassembly

```asm
0x18003ca70  push    rbx
0x18003ca72  push    rbp
0x18003ca73  push    rdi
0x18003ca74  push    r12
0x18003ca76  push    r14
0x18003ca78  push    r15
0x18003ca7a  sub     rsp, 38h
0x18003ca7e  xor     r12d, r12d
0x18003ca81  mov     rbp, r9
0x18003ca84  mov     r15, r8
0x18003ca87  mov     rdi, rdx
0x18003ca8a  mov     r14, rcx
0x18003ca8d  test    rdx, rdx
0x18003ca90  jz      loc_18003CB9E
0x18003ca96  cmp     [rdx], r12w
0x18003ca9a  jz      loc_18003CB9E
0x18003caa0  test    rcx, rcx
0x18003caa3  jz      loc_18003CB9E
0x18003caa9  test    r8, r8
0x18003caac  jz      loc_18003CB9E
0x18003cab2  mov     [rcx], r12
0x18003cab5  lea     edx, [r12+8]; Flags
0x18003caba  mov     rcx, gs:60h
0x18003cac3  lea     r8d, [r12+50h]; Size
0x18003cac8  mov     rcx, [rcx+30h]; HeapHandle
0x18003cacc  call    cs:__imp_RtlAllocateHeap
0x18003cad2  mov     rbx, rax
0x18003cad5  test    rax, rax
0x18003cad8  jnz     short loc_18003CAE4
0x18003cada  mov     edi, 0C0000017h
0x18003cadf  jmp     loc_18003CB9A
0x18003cae4  mov     rdx, rdi
0x18003cae7  mov     rcx, rbx
0x18003caea  call    AslStringDuplicate
0x18003caef  mov     edi, eax
0x18003caf1  test    eax, eax
0x18003caf3  jns     short loc_18003CB21
0x18003caf5  lea     r9, aAslstringdupli_2; "AslStringDuplicate failed [%x]"
0x18003cafc  mov     dword ptr [rsp+68h+var_48], eax
0x18003cb00  mov     r8d, 141h
0x18003cb06  lea     rdx, aAslfilemapping_4; "AslFileMappingCreateFromImageView"
0x18003cb0d  mov     ecx, 1
0x18003cb12  call    AslLogCallPrintf
0x18003cb17  mov     rcx, rbx
0x18003cb1a  call    AslFileMappingDelete
0x18003cb1f  jmp     short loc_18003CB9A
0x18003cb21  mov     dword ptr [rbx+48h], 1
0x18003cb28  lea     rcx, [rbx+8]
0x18003cb2c  mov     [rcx], r12
0x18003cb2f  lea     rdi, [rbx+38h]
0x18003cb33  mov     qword ptr [rbx+30h], 1000000h
0x18003cb3b  mov     [rbx+10h], r12
0x18003cb3f  mov     [rbx+18h], rbp
0x18003cb43  mov     [rbx+20h], r15
0x18003cb47  mov     [rbx+28h], rbp
0x18003cb4b  test    rbp, rbp
0x18003cb4e  jnz     short loc_18003CB58
0x18003cb50  mov     dword ptr [rdi], 1
0x18003cb56  jmp     short loc_18003CB94
0x18003cb58  mov     rdx, rdi
0x18003cb5b  call    AslpFileMappingGetFileKind
0x18003cb60  test    eax, eax
0x18003cb62  jns     short loc_18003CB94
0x18003cb64  mov     [rsp+68h+var_40], eax
0x18003cb68  lea     r9, aAslpfilemappin; "AslpFileMappingGetFileKind failed %S [%"...
0x18003cb6f  mov     rax, [rbx]
0x18003cb72  lea     rdx, aAslfilemapping_4; "AslFileMappingCreateFromImageView"
0x18003cb79  mov     r8d, 162h
0x18003cb7f  mov     [rsp+68h+var_48], rax
0x18003cb84  mov     ecx, 1
0x18003cb89  call    AslLogCallPrintf
0x18003cb8e  mov     dword ptr [rdi], 3
0x18003cb94  mov     [r14], rbx
0x18003cb97  mov     edi, r12d
0x18003cb9a  mov     eax, edi
0x18003cb9c  jmp     short loc_18003CBA3
0x18003cb9e  mov     eax, 0C000000Dh
0x18003cba3  add     rsp, 38h
0x18003cba7  pop     r15
0x18003cba9  pop     r14
0x18003cbab  pop     r12
0x18003cbad  pop     rdi
0x18003cbae  pop     rbp
0x18003cbaf  pop     rbx
0x18003cbb0  retn
```
