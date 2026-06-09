# Streaming::StrmPreDirectoryControl(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x140001bc0`
- end: `0x140001bf0`
- name: `?StrmPreDirectoryControl@Streaming@@YA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `48`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(PFLT_CALLBACK_DATA CallbackData, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001bc0`
- `0x14000a310`

## pseudocode

```c
__int64 __fastcall Streaming::StrmPreDirectoryControl(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_CALLBACK_DATA *a2,
        const struct _FLT_RELATED_OBJECTS *a3,
        void **a4)
{
  if ( !CallbackData || !a2 )
    return 0;
  Streaming::StagingManager::StageDirectoryInternal(
    (PFLT_INSTANCE)a2->IoStatus.Pointer,
    (PFILE_OBJECT)a2->IoStatus.Information,
    CallbackData);
  return 1;
}

```

## disassembly

```asm
0x140001bc0  sub     rsp, 28h
0x140001bc4  mov     rax, rdx
0x140001bc7  test    rcx, rcx
0x140001bca  jz      short loc_140001BE8
0x140001bcc  test    rax, rax
0x140001bcf  jz      short loc_140001BE8
0x140001bd1  mov     rdx, [rdx+20h]; FileObject
0x140001bd5  mov     r8, rcx; CallbackData
0x140001bd8  mov     rcx, [rax+18h]; Instance
0x140001bdc  call    ?StageDirectoryInternal@StagingManager@Streaming@@CAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@PEAU_FLT_CALLBACK_DATA@@@Z; Streaming::StagingManager::StageDirectoryInternal(_FLT_INSTANCE *,_FILE_OBJECT &,_FLT_CALLBACK_DATA *)
0x140001be1  mov     eax, 1
0x140001be6  jmp     short loc_140001BEA
0x140001be8  xor     eax, eax
0x140001bea  add     rsp, 28h
0x140001bee  retn
```
