# CompatTabTraceLoggingHelper::LogDXMaxWinFlag(int,ushort const *)

- ea: `0x18001010c`
- end: `0x18001029f`
- name: `?LogDXMaxWinFlag@CompatTabTraceLoggingHelper@@YAXHPEBG@Z`
- size: `403`
- prototype: `void __fastcall(CompatTabTraceLoggingHelper *__hidden this, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d14c`

## callees

- `0x1800013bc`
- `0x18000ffcc`
- `0x18001010c`
- `0x1800136f4`
- `0x180016280`

## import_xrefs

- `AEPIC!PicFreeFileInfo` at `0x18001027e`
- `AEPIC!PicFreeFileInfo` at `0x18001027e`
- `AEPIC!PicRetrieveFileInfo` at `0x180010177`
- `AEPIC!PicRetrieveFileInfo` at `0x180010177`

## pseudocode

```c
void __fastcall CompatTabTraceLoggingHelper::LogDXMaxWinFlag(
        CompatTabTraceLoggingHelper *this,
        __int64 a2,
        const unsigned __int16 *a3)
{
  int v4; // edi
  __int64 v5; // rdx
  char *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  int v9; // edx
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  char **v11; // [rsp+38h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-C0h] BYREF
  int *v13; // [rsp+60h] [rbp-A0h]
  __int64 v14; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v15; // [rsp+70h] [rbp-90h]
  int v16; // [rsp+78h] [rbp-88h]
  int v17; // [rsp+7Ch] [rbp-84h]
  char *v18; // [rsp+80h] [rbp-80h]
  int v19; // [rsp+88h] [rbp-78h]
  int v20; // [rsp+8Ch] [rbp-74h]
  unsigned __int16 v21[264]; // [rsp+90h] [rbp-70h] BYREF

  v4 = (int)this;
  v11 = 0;
  if ( !dword_180020D80 && (PiiFilter::Initialize(this), !dword_180020D80) || (int)PiiFilterExecute(v21) < 0 )
    v21[0] = 0;
  if ( (int)PicRetrieveFileInfo(a2, 0, &v11) < 0 || !v11 || (v6 = *v11) == 0 )
    v6 = byte_1800196B4;
  if ( (unsigned int)dword_180020098 > 5 )
  {
    v5 = qword_1800200B0;
    if ( (qword_1800200A8 & 0x400000000000LL) != 0 && (qword_1800200B0 & 0x400000000000LL) == qword_1800200B0 )
    {
      v7 = -1;
      v10 = v4;
      if ( v6 )
      {
        v8 = -1;
        do
          ++v8;
        while ( *(_WORD *)&v6[2 * v8] );
        v9 = 2 * v8 + 2;
      }
      else
      {
        v6 = byte_1800196B4;
        v9 = 2;
      }
      v18 = v6;
      v19 = v9;
      v20 = 0;
      do
        ++v7;
      while ( v21[v7] );
      v17 = 0;
      v16 = 2 * v7 + 2;
      v15 = v21;
      v13 = &v10;
      v14 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180020098, (unsigned __int8 *)&word_18001CEAE, 0, 0, 5u, &v12);
    }
  }
  if ( v11 )
    PicFreeFileInfo(v11, v5);
}

```

## disassembly

```asm
0x18001010c  push    rbp
0x18001010e  push    rbx
0x18001010f  push    rsi
0x180010110  push    rdi
0x180010111  lea     rbp, [rsp-1B8h]
0x180010119  sub     rsp, 2B8h
0x180010120  mov     rax, cs:__security_cookie
0x180010127  xor     rax, rsp
0x18001012a  mov     [rbp+1D0h+var_30], rax
0x180010131  xor     esi, esi
0x180010133  mov     rbx, rdx
0x180010136  cmp     cs:dword_180020D80, esi
0x18001013c  mov     edi, ecx
0x18001013e  mov     [rsp+2D0h+var_298], rsi
0x180010143  jnz     short loc_180010152
0x180010145  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x18001014a  cmp     cs:dword_180020D80, esi
0x180010150  jz      short loc_180010169
0x180010152  mov     r8, cs:?TelemetryPiiFilter@CompatTabTraceLoggingHelper@@3VPiiFilter@@A; PiiFilter CompatTabTraceLoggingHelper::TelemetryPiiFilter
0x180010159  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x18001015d  mov     r9, rbx
0x180010160  call    PiiFilterExecute
0x180010165  test    eax, eax
0x180010167  jns     short loc_18001016D
0x180010169  mov     [rbp+1D0h+var_240], si
0x18001016d  lea     r8, [rsp+2D0h+var_298]
0x180010172  xor     edx, edx
0x180010174  mov     rcx, rbx
0x180010177  call    cs:__imp_PicRetrieveFileInfo
0x18001017d  test    eax, eax
0x18001017f  js      short loc_180010193
0x180010181  mov     rcx, [rsp+2D0h+var_298]
0x180010186  test    rcx, rcx
0x180010189  jz      short loc_180010193
0x18001018b  mov     rcx, [rcx]
0x18001018e  test    rcx, rcx
0x180010191  jnz     short loc_18001019A
0x180010193  lea     rcx, byte_1800196B4
0x18001019a  mov     eax, cs:dword_180020098
0x1800101a0  cmp     eax, 5
0x1800101a3  jbe     loc_180010274
0x1800101a9  mov     rdx, cs:qword_1800200B0
0x1800101b0  mov     r8, 400000000000h
0x1800101ba  mov     rax, cs:qword_1800200A8
0x1800101c1  test    r8, rax
0x1800101c4  jz      loc_180010274
0x1800101ca  mov     rax, rdx
0x1800101cd  and     rax, r8
0x1800101d0  cmp     rax, rdx
0x1800101d3  jnz     loc_180010274
0x1800101d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800101dd  mov     [rsp+2D0h+var_2A0], edi
0x1800101e1  test    rcx, rcx
0x1800101e4  jz      short loc_1800101FB
0x1800101e6  mov     rdx, rax
0x1800101e9  inc     rdx
0x1800101ec  cmp     [rcx+rdx*2], si
0x1800101f0  jnz     short loc_1800101E9
0x1800101f2  lea     edx, ds:2[rdx*2]
0x1800101f9  jmp     short loc_180010207
0x1800101fb  lea     rcx, byte_1800196B4
0x180010202  mov     edx, 2
0x180010207  mov     [rbp+1D0h+var_250], rcx
0x18001020b  lea     rcx, [rbp+1D0h+var_240]
0x18001020f  mov     [rbp+1D0h+var_248], edx
0x180010212  mov     [rbp+1D0h+var_244], esi
0x180010215  inc     rax
0x180010218  cmp     [rcx+rax*2], si
0x18001021c  jnz     short loc_180010215
0x18001021e  lea     eax, ds:2[rax*2]
0x180010225  mov     [rsp+2D0h+var_254], esi
0x180010229  mov     [rsp+2D0h+var_258], eax
0x18001022d  lea     rcx, [rbp+1D0h+var_240]
0x180010231  lea     rax, [rsp+2D0h+var_2A0]
0x180010236  mov     [rsp+2D0h+var_260], rcx
0x18001023b  mov     [rsp+2D0h+var_270], rax
0x180010240  lea     rdx, word_18001CEAE
0x180010247  lea     rax, [rsp+2D0h+var_290]
0x18001024c  mov     [rsp+2D0h+var_268], 4
0x180010255  mov     [rsp+2D0h+var_2A8], rax
0x18001025a  lea     rcx, dword_180020098
0x180010261  xor     r9d, r9d
0x180010264  mov     [rsp+2D0h+var_2B0], 5
0x18001026c  xor     r8d, r8d
0x18001026f  call    _tlgWriteTransfer_EventWriteTransfer
0x180010274  mov     rcx, [rsp+2D0h+var_298]
0x180010279  test    rcx, rcx
0x18001027c  jz      short loc_180010284
0x18001027e  call    cs:__imp_PicFreeFileInfo
0x180010284  mov     rcx, [rbp+1D0h+var_30]
0x18001028b  xor     rcx, rsp; StackCookie
0x18001028e  call    __security_check_cookie
0x180010293  add     rsp, 2B8h
0x18001029a  pop     rdi
0x18001029b  pop     rsi
0x18001029c  pop     rbx
0x18001029d  pop     rbp
0x18001029e  retn
```
