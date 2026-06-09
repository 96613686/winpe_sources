# CFormCreds::AddThread(void *)

- ea: `0x18001c090`
- end: `0x18001c1bd`
- name: `?AddThread@CFormCreds@@AEAAXPEAX@Z`
- size: `301`
- prototype: `void __fastcall(CFormCreds *this, void *hThreadHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001c824`
- `0x18001cf5c`

## callees

- `0x18001217c`
- `0x18001c090`
- `0x18001d6c8`
- `0x18001d79c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c113`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c113`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c164`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c164`
- `ntdll!RtlEnterCriticalSection` at `0x18001c0a5`
- `ntdll!RtlEnterCriticalSection` at `0x18001c0a5`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c1b6`

## pseudocode

```c
void __fastcall CFormCreds::AddThread(CFormCreds *this, void *hThreadHandle)
{
  __int64 _a3; // rcx
  __int64 i; // rdi
  unsigned __int16 v6; // dx
  const _GUID *v7; // r8

  RtlEnterCriticalSection(&this->_cs);
  for ( _a3 = 0; (unsigned int)_a3 < 8; _a3 = (unsigned int)(_a3 + 1) )
  {
    i = (unsigned int)_a3;
    if ( !this->_Threads[_a3] )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 5u )
      {
        WPP_SF_qdq(
          WPP_GLOBAL_Control[1].Control.Logger,
          0xBu,
          (const _GUID *)WPP_GLOBAL_Control,
          this,
          _a3,
          hThreadHandle);
      }
LABEL_9:
      this->_Threads[i] = hThreadHandle;
      goto $Cleanup_5;
    }
  }
  for ( i = 0; (unsigned int)i < 8; i = (unsigned int)(i + 1) )
  {
    if ( !WaitForSingleObject(this->_Threads[i], 0) )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 5u )
      {
        WPP_SF_qdqq(WPP_GLOBAL_Control[1].Control.Logger, v6, v7, this, i, hThreadHandle, this->_Threads[i]);
      }
      CloseHandle(this->_Threads[i]);
      goto LABEL_9;
    }
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control[1].Control.Logger,
      0xDu,
      WPP_b7f12f7aa75a391fa9f50fdb5c73e71c_Traceguids,
      this,
      hThreadHandle);
  }
$Cleanup_5:
  RtlLeaveCriticalSection(&this->_cs);
}

```

## disassembly

```asm
0x18001c090  push    rbx
0x18001c092  push    rbp
0x18001c093  push    rsi
0x18001c094  push    rdi
0x18001c095  push    r14
0x18001c097  sub     rsp, 40h
0x18001c09b  mov     rbx, this
0x18001c09e  mov     rsi, hThreadHandle
0x18001c0a1  add     this, 8; CriticalSection
0x18001c0a5  call    cs:__imp_RtlEnterCriticalSection
0x18001c0ab  xor     ecx, ecx
0x18001c0ad  cmp     ecx, 8
0x18001c0b0  jnb     short loc_18001C105
0x18001c0b2  cmp     qword ptr [rbx+this*8+30h], 0
0x18001c0b8  mov     edi, ecx
0x18001c0ba  jz      short loc_18001C0C0
0x18001c0bc  inc     ecx
0x18001c0be  jmp     short loc_18001C0AD
0x18001c0c0  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001c0c7  lea     rax, WPP_GLOBAL_Control
0x18001c0ce  cmp     r8, rax
0x18001c0d1  jz      short loc_18001C0FB
0x18001c0d3  test    byte ptr [r8+44h], 8
0x18001c0d8  jz      short loc_18001C0FB
0x18001c0da  cmp     byte ptr [r8+41h], 5
0x18001c0df  jb      short loc_18001C0FB
0x18001c0e1  mov     [rsp+68h+Logger], rsi; Logger
0x18001c0e6  mov     edx, 0Bh; id
0x18001c0eb  mov     [rsp+68h+_a3], ecx; _a3
0x18001c0ef  mov     r9, rbx; _a2
0x18001c0f2  mov     this, [r8+38h]; Logger
0x18001c0f6  call    WPP_SF_qdq
0x18001c0fb  mov     [rbx+rdi*8+30h], rsi
0x18001c100  jmp     $Cleanup_5
0x18001c105  xor     edi, edi
0x18001c107  cmp     edi, 8
0x18001c10a  jnb     short loc_18001C16C
0x18001c10c  mov     this, [rbx+rdi*8+30h]; hHandle
0x18001c111  xor     edx, edx; dwMilliseconds
0x18001c113  call    cs:__imp_WaitForSingleObject
0x18001c119  test    eax, eax
0x18001c11b  jz      short loc_18001C121
0x18001c11d  inc     edi
0x18001c11f  jmp     short loc_18001C107
0x18001c121  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001c128  lea     rax, WPP_GLOBAL_Control
0x18001c12f  cmp     this, rax
0x18001c132  jz      short loc_18001C15F
0x18001c134  test    byte ptr [this+44h], 8
0x18001c138  jz      short loc_18001C15F
0x18001c13a  cmp     byte ptr [this+41h], 5
0x18001c13e  jb      short loc_18001C15F
0x18001c140  mov     rax, [rbx+rdi*8+30h]
0x18001c145  mov     r9, rbx; _a3
0x18001c148  mov     this, [this+38h]; Logger
0x18001c14c  mov     [rsp+68h+id], rax; id
0x18001c151  mov     [rsp+68h+Logger], rsi; Logger
0x18001c156  mov     [rsp+68h+_a3], edi; _a4
0x18001c15a  call    WPP_SF_qdqq
0x18001c15f  mov     this, [rbx+rdi*8+30h]; hObject
0x18001c164  call    cs:__imp_CloseHandle
0x18001c16a  jmp     short loc_18001C0FB
0x18001c16c  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001c173  lea     rax, WPP_GLOBAL_Control
0x18001c17a  cmp     this, rax
0x18001c17d  jz      short $Cleanup_5
0x18001c17f  test    byte ptr [this+44h], 8
0x18001c183  jz      short $Cleanup_5
0x18001c185  cmp     byte ptr [this+41h], 2
0x18001c189  jb      short $Cleanup_5
0x18001c18b  mov     this, [this+38h]; Logger
0x18001c18f  lea     r8, WPP_b7f12f7aa75a391fa9f50fdb5c73e71c_Traceguids; TraceGuid
0x18001c196  mov     edx, 0Dh; id
0x18001c19b  mov     qword ptr [rsp+68h+_a3], rsi; _a2
0x18001c1a0  mov     r9, rbx; _a1
0x18001c1a3  call    WPP_SF_qq
0x18001c1a8  lea     this, [rbx+8]
0x18001c1ac  add     rsp, 40h
0x18001c1b0  pop     r14
0x18001c1b2  pop     rdi
0x18001c1b3  pop     rsi
0x18001c1b4  pop     rbp
0x18001c1b5  pop     rbx
0x18001c1b6  jmp     cs:__imp_RtlLeaveCriticalSection
```
