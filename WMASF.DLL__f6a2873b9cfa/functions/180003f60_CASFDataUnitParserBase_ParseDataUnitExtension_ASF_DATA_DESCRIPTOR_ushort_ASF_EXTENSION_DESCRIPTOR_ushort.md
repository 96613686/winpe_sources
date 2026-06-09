# CASFDataUnitParserBase::ParseDataUnitExtension(_ASF_DATA_DESCRIPTOR *,ushort,ASF_EXTENSION_DESCRIPTOR *,ushort *)

- ea: `0x180003f60`
- end: `0x1800040db`
- name: `?ParseDataUnitExtension@CASFDataUnitParserBase@@UEAAJPEAU_ASF_DATA_DESCRIPTOR@@GPEAUASF_EXTENSION_DESCRIPTOR@@PEAG@Z`
- size: `379`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, struct _ASF_DATA_DESCRIPTOR *, unsigned __int16, struct ASF_EXTENSION_DESCRIPTOR *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180003a68`
- `0x180003f60`

## pseudocode

```c
__int64 __fastcall CASFDataUnitParserBase::ParseDataUnitExtension(
        struct IWMSCriticalSection **this,
        struct _ASF_DATA_DESCRIPTOR *a2,
        unsigned __int16 a3,
        struct ASF_EXTENSION_DESCRIPTOR *a4,
        unsigned __int16 *a5)
{
  unsigned __int16 *v9; // rbx
  unsigned __int16 v10; // dx
  unsigned int v11; // ebx
  struct CASFDataUnitParserBase::STREAM_INFO *v12; // r8
  unsigned __int16 v13; // ax
  unsigned int v14; // ecx
  unsigned int v15; // edi
  unsigned __int16 *v16; // rdx
  __int16 *v17; // r10
  unsigned __int16 v18; // r9
  char v20; // [rsp+50h] [rbp+8h] BYREF
  struct CASFDataUnitParserBase::STREAM_INFO *v21; // [rsp+58h] [rbp+10h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v20, this[4]);
  if ( a2 && (a4 || !a3) && (v9 = a5) != 0 )
  {
    v10 = *((_WORD *)a2 + 4);
    v21 = 0;
    if ( (int)CASFDataUnitParserBase::GetStreamInfo((CASFDataUnitParserBase *)this, v10, &v21) < 0 )
    {
      v11 = -1072887812;
LABEL_20:
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v20);
      return v11;
    }
    v12 = v21;
    v13 = *((_WORD *)v21 + 24);
    if ( a3 < v13 )
    {
      *v9 = v13;
      v11 = -1072887799;
      goto LABEL_20;
    }
    if ( !a3 )
    {
      *v9 = 0;
      v11 = 0;
      goto LABEL_20;
    }
    v14 = *((_DWORD *)a2 + 13);
    v15 = 0;
    v16 = (unsigned __int16 *)*((_QWORD *)a2 + 7);
    *v9 = 0;
    v17 = (__int16 *)*((_QWORD *)v12 + 4);
    while ( v17 )
    {
      v18 = *v17;
      *(_OWORD *)((char *)a4 + 40 * v15 + 16) = *(_OWORD *)(v17 + 2);
      if ( v18 == 0xFFFF )
      {
        if ( v14 < 2 )
          goto LABEL_19;
        *((_DWORD *)a4 + 10 * v15 + 9) = 1;
        v18 = *v16++;
        v14 -= 2;
      }
      else
      {
        *((_DWORD *)a4 + 10 * v15 + 9) = 0;
      }
      if ( v14 < v18 )
      {
LABEL_19:
        v11 = -1072887855;
        goto LABEL_20;
      }
      *((_QWORD *)a4 + 5 * v15 + 1) = v16;
      *((_WORD *)a4 + 20 * v15) = v18;
      v14 -= v18;
      *((_WORD *)a4 + 20 * v15 + 16) = (_WORD)v16 - *((_WORD *)a2 + 28);
      ++*v9;
      v17 = (__int16 *)*((_QWORD *)v17 + 3);
      v16 = (unsigned __int16 *)((char *)v16 + v18);
      ++v15;
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v20);
    return 0;
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v20);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180003f60  mov     [rsp+arg_10], rbx
0x180003f65  push    rbp
0x180003f66  push    rsi
0x180003f67  push    rdi
0x180003f68  push    r14
0x180003f6a  push    r15
0x180003f6c  sub     rsp, 20h
0x180003f70  mov     rbp, rdx
0x180003f73  mov     r14, rcx
0x180003f76  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180003f7a  mov     rsi, r9
0x180003f7d  lea     rcx, [rsp+48h+arg_0]; this
0x180003f82  movzx   edi, r8w
0x180003f86  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180003f8b  xor     r15d, r15d
0x180003f8e  test    rbp, rbp
0x180003f91  jz      loc_1800040BB
0x180003f97  test    rsi, rsi
0x180003f9a  jnz     short loc_180003FA6
0x180003f9c  cmp     r15w, di
0x180003fa0  jnz     loc_1800040BB
0x180003fa6  mov     rbx, [rsp+48h+arg_20]
0x180003fab  test    rbx, rbx
0x180003fae  jz      loc_1800040BB
0x180003fb4  movzx   edx, word ptr [rbp+8]; unsigned __int16
0x180003fb8  lea     r8, [rsp+48h+arg_8]; struct CASFDataUnitParserBase::STREAM_INFO **
0x180003fbd  mov     rcx, r14; this
0x180003fc0  mov     [rsp+48h+arg_8], r15
0x180003fc5  call    ?GetStreamInfo@CASFDataUnitParserBase@@IEAAJGPEAPEAUSTREAM_INFO@1@@Z; CASFDataUnitParserBase::GetStreamInfo(ushort,CASFDataUnitParserBase::STREAM_INFO * *)
0x180003fca  test    eax, eax
0x180003fcc  jns     short loc_180003FD8
0x180003fce  mov     ebx, 0C00D07FCh
0x180003fd3  jmp     loc_18000409F
0x180003fd8  mov     r8, [rsp+48h+arg_8]
0x180003fdd  movzx   eax, word ptr [r8+30h]
0x180003fe2  cmp     di, ax
0x180003fe5  jnb     short loc_180003FF4
0x180003fe7  mov     [rbx], ax
0x180003fea  mov     ebx, 0C00D0809h
0x180003fef  jmp     loc_18000409F
0x180003ff4  test    di, di
0x180003ff7  jnz     short loc_180004005
0x180003ff9  mov     [rbx], r15w
0x180003ffd  mov     ebx, r15d
0x180004000  jmp     loc_18000409F
0x180004005  mov     ecx, [rbp+34h]
0x180004008  mov     edi, r15d
0x18000400b  mov     rdx, [rbp+38h]
0x18000400f  mov     r14d, 1
0x180004015  mov     [rbx], r15w
0x180004019  mov     r10, [r8+20h]
0x18000401d  test    r10, r10
0x180004020  jz      loc_1800040AD
0x180004026  movzx   r9d, word ptr [r10]
0x18000402a  movups  xmm0, xmmword ptr [r10+4]
0x18000402f  mov     eax, edi
0x180004031  lea     r8, [rax+rax*4]
0x180004035  mov     eax, 0FFFFh
0x18000403a  movdqu  xmmword ptr [rsi+r8*8+10h], xmm0
0x180004041  cmp     r9w, ax
0x180004045  jnz     short loc_18000405E
0x180004047  cmp     ecx, 2
0x18000404a  jb      short loc_18000409A
0x18000404c  mov     [rsi+r8*8+24h], r14d
0x180004051  movzx   r9d, word ptr [rdx]
0x180004055  add     rdx, 2
0x180004059  add     ecx, 0FFFFFFFEh
0x18000405c  jmp     short loc_180004063
0x18000405e  mov     [rsi+r8*8+24h], r15d
0x180004063  movzx   r11d, r9w
0x180004067  cmp     ecx, r11d
0x18000406a  jb      short loc_18000409A
0x18000406c  mov     [rsi+r8*8+8], rdx
0x180004071  movzx   eax, dx
0x180004074  mov     [rsi+r8*8], r9w
0x180004079  sub     ecx, r11d
0x18000407c  sub     ax, [rbp+38h]
0x180004080  mov     [rsi+r8*8+20h], ax
0x180004086  add     [rbx], r14w
0x18000408a  mov     r10, [r10+18h]
0x18000408e  movzx   eax, r9w
0x180004092  add     rdx, rax
0x180004095  add     edi, r14d
0x180004098  jmp     short loc_18000401D
0x18000409a  mov     ebx, 0C00D07D1h
0x18000409f  lea     rcx, [rsp+48h+arg_0]; this
0x1800040a4  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800040a9  mov     eax, ebx
0x1800040ab  jmp     short loc_1800040CA
0x1800040ad  lea     rcx, [rsp+48h+arg_0]; this
0x1800040b2  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800040b7  xor     eax, eax
0x1800040b9  jmp     short loc_1800040CA
0x1800040bb  lea     rcx, [rsp+48h+arg_0]; this
0x1800040c0  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800040c5  mov     eax, 80070057h
0x1800040ca  mov     rbx, [rsp+48h+arg_10]
0x1800040cf  add     rsp, 20h
0x1800040d3  pop     r15
0x1800040d5  pop     r14
0x1800040d7  pop     rdi
0x1800040d8  pop     rsi
0x1800040d9  pop     rbp
0x1800040da  retn
```
