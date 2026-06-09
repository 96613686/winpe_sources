# Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::~TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>(void)

- ea: `0x180017e3c`
- end: `0x180017f06`
- name: `??1?$TCProducerConsumer@PEAVCDemuxIMediaSample@Mpeg2DemuxAttributes@@@Mpeg2DemuxAttributes@@QEAA@XZ`
- size: `202`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180017db4`
- `0x180022150`

## callees

- `0x180001048`
- `0x180017e3c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180017e80`
- `KERNEL32!CloseHandle` at `0x180017e80`
- `KERNEL32!DeleteCriticalSection` at `0x180017eff`
- `KERNEL32!LeaveCriticalSection` at `0x180017ee7`
- `KERNEL32!LeaveCriticalSection` at `0x180017ee7`
- `KERNEL32!EnterCriticalSection` at `0x180017e4e`
- `KERNEL32!EnterCriticalSection` at `0x180017e4e`

## pseudocode

```c
void __fastcall Mpeg2DemuxAttributes::TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>::~TCProducerConsumer<Mpeg2DemuxAttributes::CDemuxIMediaSample *>(
        LPCRITICAL_SECTION lpCriticalSection)
{
  HANDLE *p_OwningThread; // rsi
  HANDLE *OwningThread; // rcx
  HANDLE *v4; // rax
  HANDLE *v5; // rdi
  _QWORD *v6; // rdx
  bool v7; // zf
  __int64 *v8; // rdi
  _QWORD *v9; // rax
  __int64 v10; // rcx
  LPCRITICAL_SECTION v11; // rdi
  _QWORD *p_Type; // rdx
  _QWORD *v13; // rax
  __int64 v14; // rcx

  EnterCriticalSection(lpCriticalSection);
  p_OwningThread = &lpCriticalSection[1].OwningThread;
  OwningThread = (HANDLE *)lpCriticalSection[1].OwningThread;
  if ( OwningThread != &lpCriticalSection[1].OwningThread )
  {
    v4 = (HANDLE *)OwningThread[1];
    v5 = OwningThread - 3;
    v6 = *OwningThread;
    v7 = OwningThread == (HANDLE *)24;
    *v4 = *OwningThread;
    v6[1] = v4;
    while ( !v7 )
    {
      --lpCriticalSection[3].LockCount;
      CloseHandle(*v5);
      operator delete(v5, 0x28u);
      v8 = (__int64 *)*p_OwningThread;
      if ( *p_OwningThread == p_OwningThread )
        break;
      v9 = (_QWORD *)v8[1];
      v10 = *v8;
      v7 = v8 == (__int64 *)24;
      v5 = (HANDLE *)(v8 - 3);
      *v9 = v10;
      *(_QWORD *)(v10 + 8) = v9;
    }
  }
  v11 = lpCriticalSection + 1;
  while ( 1 )
  {
    p_Type = &v11->DebugInfo->Type;
    if ( (LPCRITICAL_SECTION)v11->DebugInfo == v11 )
      break;
    v13 = (_QWORD *)p_Type[1];
    v14 = *p_Type;
    *v13 = *p_Type;
    *(_QWORD *)(v14 + 8) = v13;
    if ( p_Type == (_QWORD *)8 )
      break;
    --LODWORD(lpCriticalSection[3].DebugInfo);
    operator delete(p_Type - 1, 0x18u);
  }
  LeaveCriticalSection(lpCriticalSection);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180017e3c  mov     [rsp+arg_0], rbx
0x180017e41  mov     [rsp+arg_8], rsi
0x180017e46  push    rdi
0x180017e47  sub     rsp, 20h
0x180017e4b  mov     rbx, rcx
0x180017e4e  call    cs:__imp_EnterCriticalSection
0x180017e54  lea     rsi, [rbx+38h]
0x180017e58  mov     rcx, [rsi]
0x180017e5b  cmp     rcx, rsi
0x180017e5e  jz      short loc_180017EAF
0x180017e60  mov     rax, [rcx+8]
0x180017e64  lea     rdi, [rcx-18h]
0x180017e68  mov     rdx, [rcx]
0x180017e6b  test    rdi, rdi
0x180017e6e  mov     [rax], rdx
0x180017e71  mov     [rdx+8], rax
0x180017e75  jz      short loc_180017EAF
0x180017e77  dec     dword ptr [rbx+80h]
0x180017e7d  mov     rcx, [rdi]; hObject
0x180017e80  call    cs:__imp_CloseHandle
0x180017e86  mov     edx, 28h ; '('; unsigned __int64
0x180017e8b  mov     rcx, rdi; void *
0x180017e8e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017e93  mov     rdi, [rsi]
0x180017e96  cmp     rdi, rsi
0x180017e99  jz      short loc_180017EAF
0x180017e9b  mov     rax, [rdi+8]
0x180017e9f  mov     rcx, [rdi]
0x180017ea2  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180017ea6  mov     [rax], rcx
0x180017ea9  mov     [rcx+8], rax
0x180017ead  jmp     short loc_180017E75
0x180017eaf  lea     rdi, [rbx+28h]
0x180017eb3  mov     rdx, [rdi]
0x180017eb6  cmp     rdx, rdi
0x180017eb9  jz      short loc_180017EE4
0x180017ebb  mov     rax, [rdx+8]
0x180017ebf  mov     rcx, [rdx]
0x180017ec2  mov     [rax], rcx
0x180017ec5  mov     [rcx+8], rax
0x180017ec9  lea     rax, [rdx-8]
0x180017ecd  test    rax, rax
0x180017ed0  jz      short loc_180017EE4
0x180017ed2  dec     dword ptr [rbx+78h]
0x180017ed5  mov     edx, 18h; unsigned __int64
0x180017eda  mov     rcx, rax; void *
0x180017edd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017ee2  jmp     short loc_180017EB3
0x180017ee4  mov     rcx, rbx; lpCriticalSection
0x180017ee7  call    cs:__imp_LeaveCriticalSection
0x180017eed  mov     rcx, rbx
0x180017ef0  mov     rbx, [rsp+28h+arg_0]
0x180017ef5  mov     rsi, [rsp+28h+arg_8]
0x180017efa  add     rsp, 20h
0x180017efe  pop     rdi
0x180017eff  jmp     cs:__imp_DeleteCriticalSection
```
