# CommonUtil::UtilGetVersionInfoInternal

- ea: `0x14000355c`
- end: `0x14000367e`
- name: `CommonUtil::UtilGetVersionInfoInternal`
- size: `290`
- prototype: `__int64 __fastcall(CommonUtil *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003414`

## callees

- `0x14000355c`
- `0x140005600`
- `0x140005630`
- `0x140005c20`
- `0x140005c40`
- `0x140020220`
- `0x140021e54`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetVersionInfoInternal(CommonUtil *this, _QWORD *a2, unsigned int a3)
{
  unsigned int v5; // edi
  __int64 result; // rax
  int v7; // ebx
  void *v8; // rbx
  int FileVersionInfo; // edi
  unsigned int *v10; // [rsp+20h] [rbp-30h]
  void *v11; // [rsp+28h] [rbp-28h]
  void *v12; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v13; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v14[5]; // [rsp+3Ch] [rbp-14h] BYREF

  v14[0] = 0;
  v13 = 0;
  v5 = (unsigned int)this;
  result = CommonUtil::UtilGetFileVersionInfoSize(this, a3, (const wchar_t *)v14, &v13, v10);
  if ( (int)result >= 0 )
  {
    v13 += 8;
    if ( v13 > 8 )
    {
      v12 = 0;
      v7 = CommonUtil::MpNewBuffer<unsigned char>(&v12, v13);
      if ( v7 >= 0 )
      {
        v8 = v12;
        FileVersionInfo = CommonUtil::UtilGetFileVersionInfo(
                            (CommonUtil *)v5,
                            a3,
                            (const wchar_t *)v14[0],
                            v13,
                            (unsigned int)v12,
                            v11);
        if ( FileVersionInfo >= 0 )
        {
          *a2 = v8;
          return 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              (unsigned int)WPP_1574e69935d330d50b00d67136cf9a80_Traceguids,
              a3,
              FileVersionInfo);
          if ( v8 )
            operator delete(v8);
          return (unsigned int)FileVersionInfo;
        }
      }
      else
      {
        if ( v12 )
          operator delete(v12);
        return (unsigned int)v7;
      }
    }
    else
    {
      return 2147942934LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000355c  push    rbp
0x14000355e  push    rbx
0x14000355f  push    rsi
0x140003560  push    rdi
0x140003561  push    r14
0x140003563  mov     rbp, rsp
0x140003566  sub     rsp, 50h
0x14000356a  mov     rax, cs:__security_cookie
0x140003571  xor     rax, rsp
0x140003574  mov     qword ptr [rbp+var_14+4], rax
0x140003578  mov     rsi, r8
0x14000357b  mov     [rbp+var_14], 0
0x140003582  mov     r14, rdx
0x140003585  mov     [rbp+var_18], 0
0x14000358c  mov     rdx, rsi; unsigned int
0x14000358f  lea     r9, [rbp+var_18]; unsigned int *
0x140003593  lea     r8, [rbp+var_14]; wchar_t *
0x140003597  mov     edi, ecx
0x140003599  call    ?UtilGetFileVersionInfoSize@CommonUtil@@YAJKPEB_WPEAK1@Z; CommonUtil::UtilGetFileVersionInfoSize(ulong,wchar_t const *,ulong *,ulong *)
0x14000359e  mov     ecx, eax
0x1400035a0  shr     ecx, 1Fh
0x1400035a3  test    cl, cl
0x1400035a5  jnz     loc_140003667
0x1400035ab  mov     eax, [rbp+var_18]
0x1400035ae  add     eax, 8
0x1400035b1  mov     ecx, eax
0x1400035b3  mov     [rbp+var_18], eax
0x1400035b6  cmp     eax, 8
0x1400035b9  ja      short loc_1400035C5
0x1400035bb  mov     eax, 80070216h
0x1400035c0  jmp     loc_140003667
0x1400035c5  mov     rdx, rcx
0x1400035c8  mov     [rbp+var_20], 0
0x1400035d0  lea     rcx, [rbp+var_20]
0x1400035d4  call    ??$MpNewBuffer@E@CommonUtil@@YAJPEAPEAE_K@Z; CommonUtil::MpNewBuffer<uchar>(uchar * *,unsigned __int64)
0x1400035d9  mov     ecx, eax
0x1400035db  mov     ebx, eax
0x1400035dd  shr     ecx, 1Fh
0x1400035e0  test    cl, cl
0x1400035e2  jz      short loc_1400035F6
0x1400035e4  mov     rcx, [rbp+var_20]; void *
0x1400035e8  test    rcx, rcx
0x1400035eb  jz      short loc_1400035F2
0x1400035ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400035f2  mov     eax, ebx
0x1400035f4  jmp     short loc_140003667
0x1400035f6  mov     rbx, [rbp+var_20]
0x1400035fa  mov     rdx, rsi; unsigned int
0x1400035fd  mov     r9d, [rbp+var_18]; unsigned int
0x140003601  mov     ecx, edi; this
0x140003603  mov     r8d, [rbp+var_14]; wchar_t *
0x140003607  mov     qword ptr [rsp+50h+var_30], rbx; unsigned int
0x14000360c  call    ?UtilGetFileVersionInfo@CommonUtil@@YAJKPEB_WKKPEAX@Z; CommonUtil::UtilGetFileVersionInfo(ulong,wchar_t const *,ulong,ulong,void *)
0x140003611  mov     ecx, eax
0x140003613  mov     edi, eax
0x140003615  shr     ecx, 1Fh
0x140003618  test    cl, cl
0x14000361a  jz      short loc_140003662
0x14000361c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003623  lea     rax, WPP_GLOBAL_Control
0x14000362a  cmp     rcx, rax
0x14000362d  jz      short loc_140003651
0x14000362f  test    byte ptr [rcx+1Ch], 1
0x140003633  jz      short loc_140003651
0x140003635  mov     rcx, [rcx+10h]
0x140003639  lea     r8, WPP_1574e69935d330d50b00d67136cf9a80_Traceguids
0x140003640  mov     edx, 0Ah
0x140003645  mov     [rsp+50h+var_30], edi
0x140003649  mov     r9, rsi
0x14000364c  call    WPP_SF_Sd
0x140003651  test    rbx, rbx
0x140003654  jz      short loc_14000365E
0x140003656  mov     rcx, rbx; void *
0x140003659  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000365e  mov     eax, edi
0x140003660  jmp     short loc_140003667
0x140003662  mov     [r14], rbx
0x140003665  xor     eax, eax
0x140003667  mov     rcx, qword ptr [rbp+var_14+4]
0x14000366b  xor     rcx, rsp; StackCookie
0x14000366e  call    __security_check_cookie
0x140003673  add     rsp, 50h
0x140003677  pop     r14
0x140003679  pop     rdi
0x14000367a  pop     rsi
0x14000367b  pop     rbx
0x14000367c  pop     rbp
0x14000367d  retn
```
