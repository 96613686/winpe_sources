# std::_Ref_count_resource<FaceDetectionModelRunner *,std::default_delete<FaceDetectionModelRunner>>::_Get_deleter(type_info const &)

- ea: `0x18001c730`
- end: `0x18001c75f`
- name: `?_Get_deleter@?$_Ref_count_resource@PEAVFaceDetectionModelRunner@@U?$default_delete@VFaceDetectionModelRunner@@@std@@@std@@UEBAPEAXAEBVtype_info@@@Z`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001c744`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18001c744`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_resource<FaceDetectionModelRunner *,std::default_delete<FaceDetectionModelRunner>>::_Get_deleter(
        __int64 a1,
        __int64 a2)
{
  int v3; // eax
  __int64 v4; // rdx

  v3 = __std_type_info_compare(a2 + 8, &qword_18015F1A8);
  v4 = a1 + 16;
  if ( v3 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18001c730  push    rbx
0x18001c732  sub     rsp, 20h
0x18001c736  mov     rbx, rcx
0x18001c739  lea     rcx, [rdx+8]
0x18001c73d  lea     rdx, qword_18015F1A8
0x18001c744  call    cs:__imp___std_type_info_compare
0x18001c74a  xor     ecx, ecx
0x18001c74c  lea     rdx, [rbx+10h]
0x18001c750  test    eax, eax
0x18001c752  cmovnz  rdx, rcx
0x18001c756  mov     rax, rdx
0x18001c759  add     rsp, 20h
0x18001c75d  pop     rbx
0x18001c75e  retn
```
