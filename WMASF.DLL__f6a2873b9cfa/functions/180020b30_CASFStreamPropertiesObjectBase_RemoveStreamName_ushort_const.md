# CASFStreamPropertiesObjectBase::RemoveStreamName(ushort const *)

- ea: `0x180020b30`
- end: `0x180020ca7`
- name: `?RemoveStreamName@CASFStreamPropertiesObjectBase@@UEAAJPEBG@Z`
- size: `375`
- prototype: `__int64 __fastcall(CASFStreamPropertiesObjectBase *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800011c0`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18001fc88`
- `0x180020b30`
- `0x180020cb0`
- `0x1800310c0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFStreamPropertiesObjectBase::RemoveStreamName(
        struct IWMSCriticalSection **this,
        const unsigned __int16 *a2)
{
  __int64 (__fastcall ***v4)(__int64, GUID *, __int64 *); // rcx
  int v5; // ebx
  unsigned int v6; // r15d
  unsigned int i; // ebx
  __int64 v8; // rax
  void *v9; // rsi
  int v10; // esi
  _BYTE v12[8]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v13; // [rsp+28h] [rbp-18h] BYREF
  __int16 v14; // [rsp+30h] [rbp-10h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v12, this[4]);
  v4 = (__int64 (__fastcall ***)(__int64, GUID *, __int64 *))this[5];
  if ( v4 )
  {
    v13 = 0;
    v5 = ASFGetHeaderObject(v4, &CLSID_ASFLanguageListObject, (__int64)&IID_IASFLanguageListObject, (__int64)&v13);
    if ( v5 >= 0 )
    {
      v14 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int16 *))(*(_QWORD *)v13 + 120LL))(
             v13,
             a2,
             &v14);
      if ( v13 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        v13 = 0;
      }
      if ( v5 >= 0 )
      {
        v6 = *((_DWORD *)this + 102);
        for ( i = 0; ; ++i )
        {
          if ( i >= v6 )
            goto LABEL_19;
          v8 = CTDynArray<CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20>::operator[](this + 24, i);
          v9 = (void *)v8;
          if ( v14 == *(_WORD *)v8 )
            break;
        }
        if ( !v8 )
        {
LABEL_19:
          CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v12);
          return 3222079442LL;
        }
        operator delete(*(void **)(v8 + 8));
        operator delete(v9);
        if ( i + 1 <= *((_DWORD *)this + 102) )
        {
          v10 = 0;
          while ( (int)CTSparseBlock<unsigned long,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::RemoveValue(
                         this + 24,
                         i) >= 0 )
          {
            --*((_DWORD *)this + 102);
            if ( ++v10 )
            {
              CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v12);
              return 0;
            }
          }
        }
        v5 = -2147418113;
      }
    }
  }
  else
  {
    v5 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020b30  mov     [rsp-28h+arg_10], rbx
0x180020b35  push    rbp
0x180020b36  push    rsi
0x180020b37  push    rdi
0x180020b38  push    r14
0x180020b3a  push    r15
0x180020b3c  mov     rbp, rsp
0x180020b3f  sub     rsp, 40h
0x180020b43  mov     rax, cs:__security_cookie
0x180020b4a  xor     rax, rsp
0x180020b4d  mov     [rbp+var_8], rax
0x180020b51  mov     rdi, rdx
0x180020b54  mov     r14, rcx
0x180020b57  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180020b5b  lea     rcx, [rbp+var_20]; this
0x180020b5f  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180020b64  mov     rcx, [r14+28h]
0x180020b68  test    rcx, rcx
0x180020b6b  jnz     short loc_180020B77
0x180020b6d  mov     ebx, 0C00D07F6h
0x180020b72  jmp     loc_180020C6C
0x180020b77  lea     r9, [rbp+var_18]
0x180020b7b  mov     [rbp+var_18], 0
0x180020b83  lea     r8, IID_IASFLanguageListObject
0x180020b8a  lea     rdx, CLSID_ASFLanguageListObject
0x180020b91  call    ASFGetHeaderObject
0x180020b96  mov     ebx, eax
0x180020b98  test    eax, eax
0x180020b9a  js      loc_180020C6C
0x180020ba0  mov     rcx, [rbp+var_18]
0x180020ba4  lea     r8, [rbp+var_10]
0x180020ba8  xor     eax, eax
0x180020baa  mov     rdx, rdi
0x180020bad  mov     [rbp+var_10], ax
0x180020bb1  mov     rax, [rcx]
0x180020bb4  mov     rax, [rax+78h]
0x180020bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bbd  mov     rcx, [rbp+var_18]
0x180020bc1  mov     ebx, eax
0x180020bc3  test    rcx, rcx
0x180020bc6  jz      short loc_180020BDC
0x180020bc8  mov     rax, [rcx]
0x180020bcb  mov     rax, [rax+10h]
0x180020bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bd4  mov     [rbp+var_18], 0
0x180020bdc  test    ebx, ebx
0x180020bde  js      loc_180020C6C
0x180020be4  mov     r15d, [r14+198h]
0x180020beb  xor     ebx, ebx
0x180020bed  cmp     ebx, r15d
0x180020bf0  jnb     loc_180020C79
0x180020bf6  lea     rdi, [r14+0C0h]
0x180020bfd  mov     edx, ebx
0x180020bff  mov     rcx, rdi
0x180020c02  call    ??A?$CTDynArray@PEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@$0BE@@@QEBAPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@K@Z; CTDynArray<CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20>::operator[](ulong)
0x180020c07  mov     rsi, rax
0x180020c0a  movzx   ecx, word ptr [rax]
0x180020c0d  cmp     [rbp+var_10], cx
0x180020c11  jz      short loc_180020C17
0x180020c13  inc     ebx
0x180020c15  jmp     short loc_180020BED
0x180020c17  test    rsi, rsi
0x180020c1a  jz      short loc_180020C79
0x180020c1c  mov     rcx, [rax+8]; Block
0x180020c20  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020c25  mov     edx, 10h
0x180020c2a  mov     rcx, rsi; Block
0x180020c2d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020c32  lea     eax, [rbx+1]
0x180020c35  cmp     eax, [rdi+0D8h]
0x180020c3b  ja      short loc_180020C67
0x180020c3d  xor     esi, esi
0x180020c3f  mov     edx, ebx
0x180020c41  mov     rcx, rdi
0x180020c44  call    ?RemoveValue@?$CTSparseBlock@KPEAUSTREAM_NAME_REC@CASFStreamPropertiesObjectBase@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,CASFStreamPropertiesObjectBase::STREAM_NAME_REC *,20,0>::RemoveValue(ulong)
0x180020c49  test    eax, eax
0x180020c4b  js      short loc_180020C67
0x180020c4d  dec     dword ptr [rdi+0D8h]
0x180020c53  inc     esi
0x180020c55  cmp     esi, 1
0x180020c58  jb      short loc_180020C3F
0x180020c5a  lea     rcx, [rbp+var_20]; this
0x180020c5e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180020c63  xor     eax, eax
0x180020c65  jmp     short loc_180020C87
0x180020c67  mov     ebx, 8000FFFFh
0x180020c6c  lea     rcx, [rbp+var_20]; this
0x180020c70  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180020c75  mov     eax, ebx
0x180020c77  jmp     short loc_180020C87
0x180020c79  lea     rcx, [rbp+var_20]; this
0x180020c7d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180020c82  mov     eax, 0C00D07D2h
0x180020c87  mov     rcx, [rbp+var_8]
0x180020c8b  xor     rcx, rsp; StackCookie
0x180020c8e  call    __security_check_cookie
0x180020c93  mov     rbx, [rsp+40h+arg_10]
0x180020c9b  add     rsp, 40h
0x180020c9f  pop     r15
0x180020ca1  pop     r14
0x180020ca3  pop     rdi
0x180020ca4  pop     rsi
0x180020ca5  pop     rbp
0x180020ca6  retn
```
