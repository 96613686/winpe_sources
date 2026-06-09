# CFormCreds::Cancel(void)

- ea: `0x18001c1e4`
- end: `0x18001c2ee`
- name: `?Cancel@CFormCreds@@QEAAXXZ`
- size: `266`
- prototype: `void __fastcall(CFormCreds *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180013520`

## callees

- `0x18001c1e4`
- `0x18001d6c8`
- `0x18001d72c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c21e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c273`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c28c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c21e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c273`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001c28c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c265`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c265`
- `ntdll!RtlEnterCriticalSection` at `0x18001c1fa`
- `ntdll!RtlEnterCriticalSection` at `0x18001c1fa`
- `ntdll!RtlLeaveCriticalSection` at `0x18001c2e7`

## pseudocode

```c
void __fastcall CFormCreds::Cancel(CFormCreds *this)
{
  __int64 _a4; // rbx
  int id; // esi
  void *v4; // rcx
  unsigned __int16 v5; // dx
  const _GUID *v6; // r8
  HANDLE CurrentThread; // rax
  void *v8; // rcx
  const _GUID *v9; // r8

  _a4 = 0;
  RtlEnterCriticalSection(&this->_cs);
  id = 0;
  while ( (unsigned int)_a4 < 8 )
  {
    v4 = this->_Threads[_a4];
    if ( v4 && WaitForSingleObject(v4, 0) == 258 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 5u )
      {
        WPP_SF_qdqd(WPP_GLOBAL_Control[1].Control.Logger, v5, v6, this, _a4, this->_Threads[_a4], id);
      }
      CurrentThread = GetCurrentThread();
      WaitForSingleObject(CurrentThread, 0x64u);
      if ( (unsigned int)++id >= 0xA )
      {
        do
        {
          v8 = this->_Threads[_a4];
          if ( v8
            && WaitForSingleObject(v8, 0) == 258
            && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 8) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            WPP_SF_qdq(WPP_GLOBAL_Control[1].Control.Logger, 0xFu, v9, this, _a4, this->_Threads[_a4]);
          }
          _a4 = (unsigned int)(_a4 + 1);
        }
        while ( (unsigned int)_a4 < 8 );
        break;
      }
    }
    else
    {
      _a4 = (unsigned int)(_a4 + 1);
    }
  }
  RtlLeaveCriticalSection(&this->_cs);
}

```

## disassembly

```asm
0x18001c1e4  push    rbx
0x18001c1e6  push    rbp
0x18001c1e7  push    rsi
0x18001c1e8  push    rdi
0x18001c1e9  push    r14
0x18001c1eb  push    r15
0x18001c1ed  sub     rsp, 48h
0x18001c1f1  mov     rdi, this
0x18001c1f4  xor     ebx, ebx
0x18001c1f6  add     this, 8; CriticalSection
0x18001c1fa  call    cs:__imp_RtlEnterCriticalSection
0x18001c200  xor     esi, esi
0x18001c202  lea     r15, WPP_GLOBAL_Control
0x18001c209  cmp     ebx, 8
0x18001c20c  jnb     loc_18001C2D7
0x18001c212  mov     this, [rdi+rbx*8+30h]; hHandle
0x18001c217  test    this, this
0x18001c21a  jz      short loc_18001C22B
0x18001c21c  xor     edx, edx; dwMilliseconds
0x18001c21e  call    cs:__imp_WaitForSingleObject
0x18001c224  cmp     eax, 102h
0x18001c229  jz      short loc_18001C22F
0x18001c22b  inc     ebx
0x18001c22d  jmp     short loc_18001C209
0x18001c22f  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001c236  cmp     this, r15
0x18001c239  jz      short loc_18001C265
0x18001c23b  test    byte ptr [this+44h], 8
0x18001c23f  jz      short loc_18001C265
0x18001c241  cmp     byte ptr [this+41h], 5
0x18001c245  jb      short loc_18001C265
0x18001c247  mov     rax, [rdi+rbx*8+30h]
0x18001c24c  mov     r9, rdi; _a3
0x18001c24f  mov     this, [this+38h]; Logger
0x18001c253  mov     [rsp+78h+id], esi; id
0x18001c257  mov     [rsp+78h+Logger], rax; Logger
0x18001c25c  mov     [rsp+78h+_a4], ebx; _a4
0x18001c260  call    WPP_SF_qdqd
0x18001c265  call    cs:__imp_GetCurrentThread
0x18001c26b  mov     this, rax; hHandle
0x18001c26e  mov     edx, 64h ; 'd'; dwMilliseconds
0x18001c273  call    cs:__imp_WaitForSingleObject
0x18001c279  inc     esi
0x18001c27b  cmp     esi, 0Ah
0x18001c27e  jb      short loc_18001C209
0x18001c280  mov     this, [rdi+rbx*8+30h]; hHandle
0x18001c285  test    this, this
0x18001c288  jz      short loc_18001C2D0
0x18001c28a  xor     edx, edx; dwMilliseconds
0x18001c28c  call    cs:__imp_WaitForSingleObject
0x18001c292  cmp     eax, 102h
0x18001c297  jnz     short loc_18001C2D0
0x18001c299  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18001c2a0  cmp     this, r15
0x18001c2a3  jz      short loc_18001C2D0
0x18001c2a5  test    byte ptr [this+44h], 8
0x18001c2a9  jz      short loc_18001C2D0
0x18001c2ab  cmp     byte ptr [this+41h], 2
0x18001c2af  jb      short loc_18001C2D0
0x18001c2b1  mov     rax, [rdi+rbx*8+30h]
0x18001c2b6  mov     edx, 0Fh; id
0x18001c2bb  mov     this, [this+38h]; Logger
0x18001c2bf  mov     r9, rdi; _a2
0x18001c2c2  mov     [rsp+78h+Logger], rax; Logger
0x18001c2c7  mov     [rsp+78h+_a4], ebx; _a3
0x18001c2cb  call    WPP_SF_qdq
0x18001c2d0  inc     ebx
0x18001c2d2  cmp     ebx, 8
0x18001c2d5  jb      short loc_18001C280
0x18001c2d7  lea     this, [rdi+8]
0x18001c2db  add     rsp, 48h
0x18001c2df  pop     r15
0x18001c2e1  pop     r14
0x18001c2e3  pop     rdi
0x18001c2e4  pop     rsi
0x18001c2e5  pop     rbp
0x18001c2e6  pop     rbx
0x18001c2e7  jmp     cs:__imp_RtlLeaveCriticalSection
```
