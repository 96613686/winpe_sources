# AudioFrameState::AllocateBuffer(void)

- ea: `0x18000ed68`
- end: `0x18000edca`
- name: `?AllocateBuffer@AudioFrameState@@AEAAXXZ`
- size: `98`
- prototype: `void __fastcall(AudioFrameState *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ec68`

## callees

- `0x1800019c0`
- `0x180005cd0`
- `0x18000ed68`
- `0x180039524`

## import_xrefs

- `MFPlat!MFCreateMemoryBuffer` at `0x18000ed87`
- `MFPlat!MFCreateMemoryBuffer` at `0x18000ed87`

## pseudocode

```c
void __fastcall AudioFrameState::AllocateBuffer(AudioFrameState *this)
{
  IMFMediaBuffer **v1; // rdi
  unsigned int v3; // eax
  int v4; // edx
  __int64 v5; // rdx
  __int64 v6; // r8

  v1 = (IMFMediaBuffer **)((char *)this + 40);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease((char *)this + 40);
  v3 = MFCreateMemoryBuffer(*((_DWORD *)this + 8), v1);
  MF::ThrowIfFailed((MF *)v3, v4);
  if ( g_wppLevels >= 0x20u )
    WPP_SF_qqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, this, *v1, *((_DWORD *)this + 8));
}

```

## disassembly

```asm
0x18000ed68  mov     [rsp+arg_0], rbx
0x18000ed6d  push    rdi
0x18000ed6e  sub     rsp, 30h
0x18000ed72  lea     rdi, [rcx+28h]
0x18000ed76  mov     rbx, rcx
0x18000ed79  mov     rcx, rdi
0x18000ed7c  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000ed81  mov     ecx, [rbx+20h]; cbMaxLength
0x18000ed84  mov     rdx, rdi; ppBuffer
0x18000ed87  call    cs:__imp_MFCreateMemoryBuffer
0x18000ed8d  mov     ecx, eax; this
0x18000ed8f  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000ed94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 20h ; ' '; MFWppLevels g_wppLevels
0x18000ed9b  jb      short loc_18000EDBF
0x18000ed9d  mov     eax, [rbx+20h]
0x18000eda0  mov     r9, rbx
0x18000eda3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edaa  mov     [rsp+38h+var_10], eax
0x18000edae  mov     rax, [rdi]
0x18000edb1  mov     [rsp+38h+var_18], rax
0x18000edb6  mov     rcx, [rcx+10h]
0x18000edba  call    WPP_SF_qqd
0x18000edbf  mov     rbx, [rsp+38h+arg_0]
0x18000edc4  add     rsp, 30h
0x18000edc8  pop     rdi
0x18000edc9  retn
```
