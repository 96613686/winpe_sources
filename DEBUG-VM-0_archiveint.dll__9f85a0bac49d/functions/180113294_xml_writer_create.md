# xml_writer_create

- ea: `0x180113294`
- end: `0x180113346`
- name: `xml_writer_create`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180111f54`

## callees

- `0x180113294`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1801132ab`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1801132ab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801132da`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1801132da`
- `XmlLite!CreateXmlWriter` at `0x1801132f1`
- `XmlLite!CreateXmlWriter` at `0x1801132f1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801132cb`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801132cb`

## pseudocode

```c
__int64 __fastcall xml_writer_create(void ***a1)
{
  char *v2; // rax
  void **v3; // rbx
  _QWORD *v5; // rdi
  HRESULT StreamOnHGlobal; // esi

  v2 = (char *)calloc(1u, 0x18u);
  v3 = (void **)v2;
  if ( !v2 )
    return 2147942414LL;
  v5 = v2 + 8;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, (LPSTREAM *)v2 + 1);
  if ( StreamOnHGlobal < 0 )
    goto LABEL_4;
  StreamOnHGlobal = CreateXmlWriter(&stru_180143220, v3, 0);
  if ( StreamOnHGlobal < 0 )
  {
LABEL_6:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
LABEL_4:
    free(v3);
    return (unsigned int)StreamOnHGlobal;
  }
  StreamOnHGlobal = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)*v3 + 24LL))(*v3, *v5);
  if ( StreamOnHGlobal < 0 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)*v3 + 16LL))(*v3);
    goto LABEL_6;
  }
  *a1 = v3;
  return 0;
}

```

## disassembly

```asm
0x180113294  push    rbx
0x180113296  push    rsi
0x180113297  push    rdi
0x180113298  push    r14
0x18011329a  sub     rsp, 28h
0x18011329e  mov     edx, 18h; Size
0x1801132a3  mov     r14, rcx
0x1801132a6  lea     esi, [rdx-17h]
0x1801132a9  mov     ecx, esi; Count
0x1801132ab  call    cs:__imp_calloc
0x1801132b1  mov     rbx, rax
0x1801132b4  test    rax, rax
0x1801132b7  jnz     short loc_1801132C0
0x1801132b9  mov     eax, 8007000Eh
0x1801132be  jmp     short loc_18011333C
0x1801132c0  lea     rdi, [rax+8]
0x1801132c4  mov     edx, esi; fDeleteOnRelease
0x1801132c6  mov     r8, rdi; ppstm
0x1801132c9  xor     ecx, ecx; hGlobal
0x1801132cb  call    cs:__imp_CreateStreamOnHGlobal
0x1801132d1  mov     esi, eax
0x1801132d3  test    eax, eax
0x1801132d5  jns     short loc_1801132E4
0x1801132d7  mov     rcx, rbx; Block
0x1801132da  call    cs:__imp_free
0x1801132e0  mov     eax, esi
0x1801132e2  jmp     short loc_18011333C
0x1801132e4  xor     r8d, r8d; pMalloc
0x1801132e7  lea     rcx, stru_180143220; riid
0x1801132ee  mov     rdx, rbx; ppvObject
0x1801132f1  call    cs:__imp_CreateXmlWriter
0x1801132f7  mov     esi, eax
0x1801132f9  test    eax, eax
0x1801132fb  jns     short loc_18011330E
0x1801132fd  mov     rcx, [rdi]
0x180113300  mov     rdx, [rcx]
0x180113303  mov     rax, [rdx+10h]
0x180113307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011330c  jmp     short loc_1801132D7
0x18011330e  mov     rcx, [rbx]
0x180113311  mov     rdx, [rdi]
0x180113314  mov     rax, [rcx]
0x180113317  mov     rax, [rax+18h]
0x18011331b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113320  mov     esi, eax
0x180113322  test    eax, eax
0x180113324  jns     short loc_180113337
0x180113326  mov     rcx, [rbx]
0x180113329  mov     rdx, [rcx]
0x18011332c  mov     rax, [rdx+10h]
0x180113330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113335  jmp     short loc_1801132FD
0x180113337  mov     [r14], rbx
0x18011333a  xor     eax, eax
0x18011333c  add     rsp, 28h
0x180113340  pop     r14
0x180113342  pop     rdi
0x180113343  pop     rsi
0x180113344  pop     rbx
0x180113345  retn
```
