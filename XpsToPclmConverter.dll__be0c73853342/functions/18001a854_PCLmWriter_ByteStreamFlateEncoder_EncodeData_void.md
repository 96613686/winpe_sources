# PCLmWriter::ByteStreamFlateEncoder::_EncodeData(void)

- ea: `0x18001a854`
- end: `0x18001ab0e`
- name: `?_EncodeData@ByteStreamFlateEncoder@PCLmWriter@@AEAA_NXZ`
- size: `698`
- prototype: `bool __fastcall(PCLmWriter::ByteStreamFlateEncoder *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x18001a7d0`

## callees

- `0x1800015f0`
- `0x180002148`
- `0x180002154`
- `0x1800030b0`
- `0x180003b00`
- `0x180003d20`
- `0x18000e7c8`
- `0x18000f448`
- `0x1800101cc`
- `0x180010f34`
- `0x180013028`
- `0x18001496c`
- `0x180018334`
- `0x1800184f0`
- `0x18001a754`
- `0x18001a854`
- `0x18001ab14`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall PCLmWriter::ByteStreamFlateEncoder::_EncodeData(PCLmWriter::ByteStreamFlateEncoder *this)
{
  char *v2; // r12
  std::_Ref_count_base *v3; // rbx
  char v4; // r14
  __int64 v5; // rax
  unsigned int v6; // eax
  size_t v7; // r15
  char *v8; // rsi
  size_t v9; // rbx
  int v10; // eax
  char *v11; // rsi
  char *v12; // rax
  size_t v13; // rbx
  char *v14; // rsi
  signed __int64 v15; // rbx
  unsigned __int64 v16; // rdx
  char *v17; // rax
  void *v19[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+30h] [rbp-D0h]
  std::_Ref_count_base *v21[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 ByteStreamBuffer; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+58h] [rbp-A8h]
  char *v24; // [rsp+60h] [rbp-A0h]
  int v25; // [rsp+68h] [rbp-98h]
  unsigned int v26; // [rsp+6Ch] [rbp-94h]
  _BYTE pExceptionObject[64]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = (char *)this + 80;
  v3 = (std::_Ref_count_base *)(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 16LL))(*((_QWORD *)this + 10));
  std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(v19);
  v21[0] = v3;
  if ( (unsigned __int64)v3 > v20 - (unsigned __int64)v19[0] )
    std::vector<unsigned char>::_Reallocate<0>(v19, v21);
  v4 = 0;
  PCLmWriter::FlateEncoderWrapper::FlateEncoderWrapper((PCLmWriter::FlateEncoderWrapper *)&ByteStreamBuffer);
  v5 = std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v21, v2);
  ByteStreamBuffer = PCLmWriter::GetByteStreamBuffer(v5);
  v23 = (int)v3;
  v6 = deflateBound(&ByteStreamBuffer, (unsigned int)v3);
  v7 = v6;
  v8 = (char *)v19[1];
  if ( (void *)v6 >= (void *)((char *)v19[1] - (char *)v19[0]) )
  {
    if ( (void *)v6 > (void *)((char *)v19[1] - (char *)v19[0]) )
    {
      if ( v6 <= v20 - (unsigned __int64)v19[0] )
      {
        v9 = v6 - (unsigned __int64)((char *)v19[1] - (char *)v19[0]);
        memset_0(v19[1], 0, v9);
        v19[1] = &v8[v9];
      }
      else
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v19, v6);
      }
    }
  }
  else
  {
    v19[1] = (char *)v19[0] + v6;
  }
  v24 = (char *)v19[0];
LABEL_10:
  v25 = v7;
  while ( !v4 )
  {
    v10 = deflate(&ByteStreamBuffer, 4);
    if ( v10 != 1 )
    {
      if ( v10 )
      {
        v21[0] = (std::_Ref_count_base *)"Error zlib::encode failed!";
        PCLmWriter::ByteStreamException::ByteStreamException(
          (PCLmWriter::ByteStreamException *)pExceptionObject,
          (const char *const *)v21,
          -2147187197);
        throw (PCLmWriter::ByteStreamException *)pExceptionObject;
      }
      v14 = (char *)v19[1];
      v15 = (char *)v19[1] - (char *)v19[0];
      v16 = (char *)v19[1] - (char *)v19[0] + v7;
      if ( v16 < (char *)v19[1] - (char *)v19[0] )
      {
        v17 = (char *)v19[1] + v7;
        goto LABEL_28;
      }
      if ( v16 > (char *)v19[1] - (char *)v19[0] )
      {
        if ( v16 <= v20 - (unsigned __int64)v19[0] )
        {
          memset_0(v19[1], 0, v7);
          v17 = &v14[v7];
LABEL_28:
          v19[1] = v17;
        }
        else
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v19, v16);
        }
      }
      v24 = (char *)v19[0] + v15;
      goto LABEL_10;
    }
    v11 = (char *)v19[1];
    if ( (void *)v26 >= (void *)((char *)v19[1] - (char *)v19[0]) )
    {
      if ( (void *)v26 <= (void *)((char *)v19[1] - (char *)v19[0]) )
        goto LABEL_20;
      if ( v26 > v20 - (unsigned __int64)v19[0] )
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v19, v26);
        goto LABEL_20;
      }
      v13 = v26 - (unsigned __int64)((char *)v19[1] - (char *)v19[0]);
      memset_0(v19[1], 0, v13);
      v12 = &v11[v13];
    }
    else
    {
      v12 = (char *)v19[0] + v26;
    }
    v19[1] = v12;
LABEL_20:
    v4 = 1;
  }
  if ( (void **)((char *)this + 40) != v19 )
  {
    std::vector<unsigned char>::_Tidy((char *)this + 40);
    *(_OWORD *)((char *)this + 40) = *(_OWORD *)v19;
    *((_QWORD *)this + 7) = v20;
    *(_OWORD *)v19 = 0;
    v20 = 0;
  }
  *(_OWORD *)v21 = 0;
  std::shared_ptr<PCLmWriter::IByteStream>::operator=(v2, v21);
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
  deflateEnd(&ByteStreamBuffer);
  std::vector<unsigned char>::_Tidy(v19);
  return v4;
}

```

## disassembly

```asm
0x18001a854  push    rbp
0x18001a856  push    rbx
0x18001a857  push    rsi
0x18001a858  push    rdi
0x18001a859  push    r12
0x18001a85b  push    r13
0x18001a85d  push    r14
0x18001a85f  push    r15
0x18001a861  lea     rbp, [rsp-8]
0x18001a866  sub     rsp, 108h
0x18001a86d  mov     rax, cs:__security_cookie
0x18001a874  xor     rax, rsp
0x18001a877  mov     [rbp+40h+var_50], rax
0x18001a87b  mov     r13, rcx
0x18001a87e  lea     r12, [rcx+50h]
0x18001a882  mov     rcx, [r12]
0x18001a886  mov     rax, [rcx]
0x18001a889  mov     rax, [rax+10h]
0x18001a88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a892  mov     ebx, eax
0x18001a894  lea     rcx, [rsp+140h+var_120]
0x18001a899  call    ??0?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<PCLmWriter::IObject const>>::vector<std::shared_ptr<PCLmWriter::IObject const>>(void)
0x18001a89e  nop
0x18001a89f  mov     [rsp+140h+var_108], rbx
0x18001a8a4  mov     rcx, [rsp+140h+var_110]
0x18001a8a9  sub     rcx, [rsp+140h+var_120]
0x18001a8ae  cmp     rbx, rcx
0x18001a8b1  jbe     short loc_18001A8C2
0x18001a8b3  lea     rdx, [rsp+140h+var_108]
0x18001a8b8  lea     rcx, [rsp+140h+var_120]
0x18001a8bd  call    ??$_Reallocate@$0A@@?$vector@EV?$allocator@E@std@@@std@@AEAAXAEA_K@Z; std::vector<uchar>::_Reallocate<0>(unsigned __int64 &)
0x18001a8c2  xor     r14b, r14b
0x18001a8c5  lea     rcx, [rsp+140h+var_F0]; this
0x18001a8ca  call    ??0FlateEncoderWrapper@PCLmWriter@@QEAA@XZ; PCLmWriter::FlateEncoderWrapper::FlateEncoderWrapper(void)
0x18001a8cf  nop
0x18001a8d0  mov     rdx, r12
0x18001a8d3  lea     rcx, [rsp+140h+var_108]
0x18001a8d8  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x18001a8dd  mov     rcx, rax
0x18001a8e0  call    ?GetByteStreamBuffer@PCLmWriter@@YAPEAEV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@Z; PCLmWriter::GetByteStreamBuffer(std::shared_ptr<PCLmWriter::IByteStream>)
0x18001a8e5  mov     [rsp+140h+var_F0], rax
0x18001a8ea  mov     [rsp+140h+var_E8], ebx
0x18001a8ee  mov     edx, ebx
0x18001a8f0  lea     rcx, [rsp+140h+var_F0]
0x18001a8f5  call    deflateBound
0x18001a8fa  mov     r15d, eax
0x18001a8fd  mov     rdx, [rsp+140h+var_120]
0x18001a902  mov     rsi, [rsp+140h+var_120+8]
0x18001a907  mov     rcx, rsi
0x18001a90a  sub     rcx, rdx
0x18001a90d  cmp     r15, rcx
0x18001a910  jnb     short loc_18001A91D
0x18001a912  lea     rcx, [r15+rdx]
0x18001a916  mov     [rsp+140h+var_120+8], rcx
0x18001a91b  jmp     short loc_18001A957
0x18001a91d  jbe     short loc_18001A957
0x18001a91f  mov     rax, [rsp+140h+var_110]
0x18001a924  sub     rax, rdx
0x18001a927  cmp     r15, rax
0x18001a92a  jbe     short loc_18001A93B
0x18001a92c  mov     rdx, r15
0x18001a92f  lea     rcx, [rsp+140h+var_120]
0x18001a934  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001a939  jmp     short loc_18001A957
0x18001a93b  mov     rbx, r15
0x18001a93e  sub     rbx, rcx
0x18001a941  mov     r8, rbx; Size
0x18001a944  xor     edx, edx; Val
0x18001a946  mov     rcx, rsi; void *
0x18001a949  call    memset_0
0x18001a94e  lea     rax, [rbx+rsi]
0x18001a952  mov     [rsp+140h+var_120+8], rax
0x18001a957  mov     rax, [rsp+140h+var_120]
0x18001a95c  mov     [rsp+140h+var_E0], rax
0x18001a961  mov     [rsp+140h+var_D8], r15d
0x18001a966  test    r14b, r14b
0x18001a969  jnz     loc_18001AA75
0x18001a96f  mov     edx, 4
0x18001a974  lea     rcx, [rsp+140h+var_F0]
0x18001a979  call    deflate
0x18001a97e  cmp     eax, 1
0x18001a981  jnz     short loc_18001A9DE
0x18001a983  mov     rdx, [rsp+140h+var_120]
0x18001a988  mov     rsi, [rsp+140h+var_120+8]
0x18001a98d  mov     rcx, rsi
0x18001a990  sub     rcx, rdx
0x18001a993  mov     ebx, [rsp+140h+var_D4]
0x18001a997  cmp     rbx, rcx
0x18001a99a  jnb     short loc_18001A9A2
0x18001a99c  lea     rax, [rbx+rdx]
0x18001a9a0  jmp     short loc_18001A9D4
0x18001a9a2  jbe     short loc_18001A9D9
0x18001a9a4  mov     rax, [rsp+140h+var_110]
0x18001a9a9  sub     rax, rdx
0x18001a9ac  cmp     rbx, rax
0x18001a9af  jbe     short loc_18001A9C0
0x18001a9b1  mov     rdx, rbx
0x18001a9b4  lea     rcx, [rsp+140h+var_120]
0x18001a9b9  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001a9be  jmp     short loc_18001A9D9
0x18001a9c0  sub     rbx, rcx
0x18001a9c3  mov     r8, rbx; Size
0x18001a9c6  xor     edx, edx; Val
0x18001a9c8  mov     rcx, rsi; void *
0x18001a9cb  call    memset_0
0x18001a9d0  lea     rax, [rbx+rsi]
0x18001a9d4  mov     [rsp+140h+var_120+8], rax
0x18001a9d9  mov     r14b, 1
0x18001a9dc  jmp     short loc_18001A966
0x18001a9de  test    eax, eax
0x18001a9e0  jnz     short loc_18001AA44
0x18001a9e2  mov     rcx, [rsp+140h+var_120]
0x18001a9e7  mov     rsi, [rsp+140h+var_120+8]
0x18001a9ec  mov     rbx, rsi
0x18001a9ef  sub     rbx, rcx
0x18001a9f2  lea     rdx, [rbx+r15]
0x18001a9f6  cmp     rdx, rbx
0x18001a9f9  jnb     short loc_18001AA01
0x18001a9fb  lea     rax, [rdx+rcx]
0x18001a9ff  jmp     short loc_18001AA2D
0x18001aa01  jbe     short loc_18001AA32
0x18001aa03  mov     rax, [rsp+140h+var_110]
0x18001aa08  sub     rax, rcx
0x18001aa0b  cmp     rdx, rax
0x18001aa0e  jbe     short loc_18001AA1C
0x18001aa10  lea     rcx, [rsp+140h+var_120]
0x18001aa15  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001aa1a  jmp     short loc_18001AA32
0x18001aa1c  mov     r8, r15; Size
0x18001aa1f  xor     edx, edx; Val
0x18001aa21  mov     rcx, rsi; void *
0x18001aa24  call    memset_0
0x18001aa29  lea     rax, [r15+rsi]
0x18001aa2d  mov     [rsp+140h+var_120+8], rax
0x18001aa32  mov     rcx, [rsp+140h+var_120]
0x18001aa37  add     rcx, rbx
0x18001aa3a  mov     [rsp+140h+var_E0], rcx
0x18001aa3f  jmp     loc_18001A961
0x18001aa44  lea     rax, aErrorZlibEncod; "Error zlib::encode failed!"
0x18001aa4b  mov     [rsp+140h+var_108], rax
0x18001aa50  mov     r8d, 80048603h; int
0x18001aa56  lea     rdx, [rsp+140h+var_108]; char **
0x18001aa5b  lea     rcx, [rbp+40h+pExceptionObject]; this
0x18001aa5f  call    ??0ByteStreamException@PCLmWriter@@QEAA@AEBQEBDJ@Z; PCLmWriter::ByteStreamException::ByteStreamException(char const * const &,long)
0x18001aa64  lea     rdx, _TI3?AVByteStreamException@PCLmWriter@@; pThrowInfo
0x18001aa6b  lea     rcx, [rbp+40h+pExceptionObject]; pExceptionObject
0x18001aa6f  call    _CxxThrowException_0
0x18001aa75  lea     rbx, [r13+28h]
0x18001aa79  lea     rax, [rsp+140h+var_120]
0x18001aa7e  cmp     rbx, rax
0x18001aa81  jz      short loc_18001AAB0
0x18001aa83  mov     rcx, rbx
0x18001aa86  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001aa8b  movups  xmm0, xmmword ptr [rsp+140h+var_120]
0x18001aa90  movups  xmmword ptr [rbx], xmm0
0x18001aa93  movsd   xmm1, [rsp+140h+var_110]
0x18001aa99  movsd   qword ptr [rbx+10h], xmm1
0x18001aa9e  xorps   xmm0, xmm0
0x18001aaa1  movdqu  xmmword ptr [rsp+140h+var_120], xmm0
0x18001aaa7  mov     [rsp+140h+var_110], 0
0x18001aab0  xorps   xmm0, xmm0
0x18001aab3  movdqu  xmmword ptr [rsp+140h+var_108], xmm0
0x18001aab9  lea     rdx, [rsp+140h+var_108]
0x18001aabe  mov     rcx, r12
0x18001aac1  call    ??4?$shared_ptr@VIByteStream@PCLmWriter@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<PCLmWriter::IByteStream>::operator=(std::shared_ptr<PCLmWriter::IByteStream> &&)
0x18001aac6  mov     rcx, [rsp+140h+var_108+8]; this
0x18001aacb  test    rcx, rcx
0x18001aace  jz      short loc_18001AAD6
0x18001aad0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001aad5  nop
0x18001aad6  lea     rcx, [rsp+140h+var_F0]
0x18001aadb  call    deflateEnd
0x18001aae0  nop
0x18001aae1  lea     rcx, [rsp+140h+var_120]
0x18001aae6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001aaeb  mov     al, r14b
0x18001aaee  mov     rcx, [rbp+40h+var_50]
0x18001aaf2  xor     rcx, rsp; StackCookie
0x18001aaf5  call    __security_check_cookie
0x18001aafa  add     rsp, 108h
0x18001ab01  pop     r15
0x18001ab03  pop     r14
0x18001ab05  pop     r13
0x18001ab07  pop     r12
0x18001ab09  pop     rdi
0x18001ab0a  pop     rsi
0x18001ab0b  pop     rbx
0x18001ab0c  pop     rbp
0x18001ab0d  retn
```
