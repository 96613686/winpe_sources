# CGestureRecognizer::_AddStroke(void *)

- ea: `0x1800fbe74`
- end: `0x1800fc050`
- name: `?_AddStroke@CGestureRecognizer@@AEAAJPEAX@Z`
- size: `476`
- prototype: `int(CGestureRecognizer *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800fc058`

## callees

- `0x18003312c`
- `0x180034e54`
- `0x180034fb0`
- `0x18007dff8`
- `0x180085e3c`
- `0x1800fbe74`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fbf1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fbf39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fbf8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fbf1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fbf39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fbf8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc01f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800fc01f`

## pseudocode

```c
__int64 __fastcall CGestureRecognizer::_AddStroke(CGestureRecognizer *this, CInkStroke *a2)
{
  HRESULT PointCount; // ebx
  __int64 v4; // r15
  ULONG v5; // r13d
  BYTE *v6; // rax
  BYTE *v7; // rsi
  unsigned int v8; // r12d
  int RawInkPacket; // eax
  unsigned int v11; // [rsp+30h] [rbp-29h] BYREF
  BYTE *v12; // [rsp+38h] [rbp-21h] BYREF
  PACKET_DESCRIPTION pPacketDesc; // [rsp+40h] [rbp-19h] BYREF
  CGestureRecognizer *v14; // [rsp+60h] [rbp+7h]
  XFORM pXForm; // [rsp+68h] [rbp+Fh] BYREF

  v14 = this;
  v11 = 0;
  LODWORD(v12) = 0;
  memset(&pXForm, 0, sizeof(pXForm));
  memset(&pPacketDesc, 0, sizeof(pPacketDesc));
  PointCount = InkStroke_GetPointCount(a2, &v11);
  if ( PointCount >= 0 )
  {
    PointCount = InkStroke_GetInkPacketSize(a2, &v12);
    if ( PointCount >= 0 )
    {
      PointCount = InkStroke_GetPacketDescription(a2, &pPacketDesc);
      if ( PointCount >= 0 )
      {
        if ( pPacketDesc.cPacketProperties )
        {
          pPacketDesc.pPacketProperties = (PACKET_PROPERTY *)CoTaskMemAlloc(32LL * pPacketDesc.cPacketProperties);
          if ( !pPacketDesc.pPacketProperties )
            goto LABEL_12;
        }
        if ( pPacketDesc.cButtons )
        {
          pPacketDesc.pguidButtons = (GUID *)CoTaskMemAlloc(16LL * pPacketDesc.cButtons);
          if ( !pPacketDesc.pguidButtons )
            goto LABEL_12;
        }
        PointCount = InkStroke_GetPacketDescription(a2, &pPacketDesc);
        if ( PointCount >= 0 )
        {
          if ( v11 )
          {
            v4 = (unsigned int)v12;
            if ( (unsigned int)v12 * (unsigned __int64)v11 < 0xFFFFFFFF )
            {
              v5 = v11 * (_DWORD)v12;
              v6 = (BYTE *)CoTaskMemAlloc(v11 * (unsigned int)v12);
              v7 = v6;
              if ( !v6 )
              {
LABEL_12:
                PointCount = -2147024882;
                goto LABEL_19;
              }
              v8 = 0;
              v12 = v6;
              while ( v8 < v11 )
              {
                RawInkPacket = InkStroke_GetRawInkPacket(a2, v8++, (struct tagXFORM *)&pXForm);
                PointCount = RawInkPacket;
                v12 += v4;
                if ( RawInkPacket < 0 )
                  goto LABEL_18;
              }
              PointCount = AddStroke(*((HRECOCONTEXT *)v14 + 16), &pPacketDesc, v5, v7, &pXForm);
LABEL_18:
              CoTaskMemFree(v7);
            }
          }
        }
      }
    }
  }
LABEL_19:
  if ( pPacketDesc.pPacketProperties )
    CoTaskMemFree(pPacketDesc.pPacketProperties);
  if ( pPacketDesc.pguidButtons )
    CoTaskMemFree(pPacketDesc.pguidButtons);
  return (unsigned int)PointCount;
}

```

## disassembly

```asm
0x1800fbe74  mov     [rsp-8+arg_10], rbx
0x1800fbe79  mov     [rsp-8+arg_18], rsi
0x1800fbe7e  push    rbp
0x1800fbe7f  push    r12
0x1800fbe81  push    r13
0x1800fbe83  push    r14
0x1800fbe85  push    r15
0x1800fbe87  lea     rbp, [rsp-37h]
0x1800fbe8c  sub     rsp, 90h
0x1800fbe93  mov     rax, cs:__security_cookie
0x1800fbe9a  xor     rax, rsp
0x1800fbe9d  mov     [rbp+57h+var_30], rax
0x1800fbea1  mov     r14, rdx
0x1800fbea4  mov     [rbp+57h+var_50], rcx
0x1800fbea8  xorps   xmm1, xmm1
0x1800fbeab  mov     [rbp+57h+var_80], 0
0x1800fbeb2  xorps   xmm0, xmm0
0x1800fbeb5  mov     dword ptr [rbp+57h+var_78], 0
0x1800fbebc  xor     eax, eax
0x1800fbebe  lea     rdx, [rbp+57h+var_80]
0x1800fbec2  mov     rcx, r14
0x1800fbec5  mov     qword ptr [rbp+57h+var_48.eDx], rax
0x1800fbec9  movups  xmmword ptr [rbp+57h+var_48.eM11], xmm0
0x1800fbecd  movups  xmmword ptr [rbp+57h+pPacketDesc.cbPacketSize], xmm1
0x1800fbed1  movups  xmmword ptr [rbp+57h+pPacketDesc.cButtons], xmm1
0x1800fbed5  call    InkStroke_GetPointCount
0x1800fbeda  mov     ebx, eax
0x1800fbedc  test    eax, eax
0x1800fbede  js      loc_1800FC007
0x1800fbee4  lea     rdx, [rbp+57h+var_78]
0x1800fbee8  mov     rcx, r14
0x1800fbeeb  call    InkStroke_GetInkPacketSize
0x1800fbef0  mov     ebx, eax
0x1800fbef2  test    eax, eax
0x1800fbef4  js      loc_1800FC007
0x1800fbefa  lea     rdx, [rbp+57h+pPacketDesc]
0x1800fbefe  mov     rcx, r14
0x1800fbf01  call    InkStroke_GetPacketDescription
0x1800fbf06  mov     ebx, eax
0x1800fbf08  test    eax, eax
0x1800fbf0a  js      loc_1800FC007
0x1800fbf10  mov     eax, [rbp+57h+pPacketDesc.cPacketProperties]
0x1800fbf13  test    eax, eax
0x1800fbf15  jz      short loc_1800FBF2C
0x1800fbf17  mov     ecx, eax
0x1800fbf19  shl     rcx, 5; cb
0x1800fbf1d  call    cs:__imp_CoTaskMemAlloc
0x1800fbf23  mov     [rbp+57h+pPacketDesc.pPacketProperties], rax
0x1800fbf27  test    rax, rax
0x1800fbf2a  jz      short loc_1800FBF9B
0x1800fbf2c  mov     eax, [rbp+57h+pPacketDesc.cButtons]
0x1800fbf2f  test    eax, eax
0x1800fbf31  jz      short loc_1800FBF48
0x1800fbf33  mov     ecx, eax
0x1800fbf35  shl     rcx, 4; cb
0x1800fbf39  call    cs:__imp_CoTaskMemAlloc
0x1800fbf3f  mov     [rbp+57h+pPacketDesc.pguidButtons], rax
0x1800fbf43  test    rax, rax
0x1800fbf46  jz      short loc_1800FBF9B
0x1800fbf48  lea     rdx, [rbp+57h+pPacketDesc]
0x1800fbf4c  mov     rcx, r14
0x1800fbf4f  call    InkStroke_GetPacketDescription
0x1800fbf54  mov     ebx, eax
0x1800fbf56  test    eax, eax
0x1800fbf58  js      loc_1800FC007
0x1800fbf5e  cmp     [rbp+57h+var_80], 0
0x1800fbf62  jbe     loc_1800FC007
0x1800fbf68  mov     r15d, dword ptr [rbp+57h+var_78]
0x1800fbf6c  mov     ecx, 0FFFFFFFFh
0x1800fbf71  mov     eax, [rbp+57h+var_80]
0x1800fbf74  imul    rax, r15
0x1800fbf78  cmp     rax, rcx
0x1800fbf7b  jnb     loc_1800FC007
0x1800fbf81  mov     eax, r15d
0x1800fbf84  imul    eax, [rbp+57h+var_80]
0x1800fbf88  mov     ecx, eax; cb
0x1800fbf8a  mov     r13d, eax
0x1800fbf8d  call    cs:__imp_CoTaskMemAlloc
0x1800fbf93  mov     rsi, rax
0x1800fbf96  test    rax, rax
0x1800fbf99  jnz     short loc_1800FBFA2
0x1800fbf9b  mov     ebx, 8007000Eh
0x1800fbfa0  jmp     short loc_1800FC007
0x1800fbfa2  mov     rcx, rsi
0x1800fbfa5  xor     r12d, r12d
0x1800fbfa8  mov     [rbp+57h+var_78], rcx
0x1800fbfac  lea     rax, [rbp+57h+var_48]
0x1800fbfb0  mov     [rsp+0B0h+pXForm], rax; struct tagXFORM *
0x1800fbfb5  cmp     r12d, [rbp+57h+var_80]
0x1800fbfb9  jnb     short loc_1800FBFE2
0x1800fbfbb  mov     r9, rcx
0x1800fbfbe  mov     r8d, r15d
0x1800fbfc1  mov     rcx, r14; this
0x1800fbfc4  mov     edx, r12d; int
0x1800fbfc7  call    InkStroke_GetRawInkPacket
0x1800fbfcc  mov     rcx, [rbp+57h+var_78]
0x1800fbfd0  inc     r12d
0x1800fbfd3  add     rcx, r15
0x1800fbfd6  mov     ebx, eax
0x1800fbfd8  mov     [rbp+57h+var_78], rcx
0x1800fbfdc  test    eax, eax
0x1800fbfde  jns     short loc_1800FBFAC
0x1800fbfe0  jmp     short loc_1800FBFFE
0x1800fbfe2  mov     rcx, [rbp+57h+var_50]
0x1800fbfe6  lea     rdx, [rbp+57h+pPacketDesc]; pPacketDesc
0x1800fbfea  mov     r9, rsi; pPacket
0x1800fbfed  mov     r8d, r13d; cbPacket
0x1800fbff0  mov     rcx, [rcx+80h]; hrc
0x1800fbff7  call    AddStroke
0x1800fbffc  mov     ebx, eax
0x1800fbffe  mov     rcx, rsi; pv
0x1800fc001  call    cs:__imp_CoTaskMemFree
0x1800fc007  mov     rcx, [rbp+57h+pPacketDesc.pPacketProperties]; pv
0x1800fc00b  test    rcx, rcx
0x1800fc00e  jz      short loc_1800FC016
0x1800fc010  call    cs:__imp_CoTaskMemFree
0x1800fc016  mov     rcx, [rbp+57h+pPacketDesc.pguidButtons]; pv
0x1800fc01a  test    rcx, rcx
0x1800fc01d  jz      short loc_1800FC025
0x1800fc01f  call    cs:__imp_CoTaskMemFree
0x1800fc025  mov     eax, ebx
0x1800fc027  mov     rcx, [rbp+57h+var_30]
0x1800fc02b  xor     rcx, rsp; StackCookie
0x1800fc02e  call    __security_check_cookie
0x1800fc033  lea     r11, [rsp+0B0h+var_20]
0x1800fc03b  mov     rbx, [r11+40h]
0x1800fc03f  mov     rsi, [r11+48h]
0x1800fc043  mov     rsp, r11
0x1800fc046  pop     r15
0x1800fc048  pop     r14
0x1800fc04a  pop     r13
0x1800fc04c  pop     r12
0x1800fc04e  pop     rbp
0x1800fc04f  retn
```
