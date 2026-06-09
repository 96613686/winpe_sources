# CASFMetaDataObjectBase::GetDescriptorCountForStream(ushort,ushort *)

- ea: `0x1800257d0`
- end: `0x180025882`
- name: `?GetDescriptorCountForStream@CASFMetaDataObjectBase@@UEAAJGPEAG@Z`
- size: `178`
- prototype: `__int64 __fastcall(CASFMetaDataObjectBase *__hidden this, unsigned __int16, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x180024b8c`
- `0x1800257d0`

## pseudocode

```c
__int64 __fastcall CASFMetaDataObjectBase::GetDescriptorCountForStream(
        struct IWMSCriticalSection **this,
        __int16 a2,
        unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  unsigned __int16 v7; // si
  _BYTE v9[2]; // [rsp+20h] [rbp-38h] BYREF
  __int16 v10; // [rsp+22h] [rbp-36h]
  char v11; // [rsp+60h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v11, this[4]);
  if ( this[5] )
  {
    if ( a3 )
    {
      if ( a2 == -1 )
      {
        *a3 = *((_WORD *)this + 400);
      }
      else
      {
        v7 = 0;
        for ( *a3 = 0; v7 < *((_WORD *)this + 400); ++v7 )
        {
          CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](this + 10, v9, v7);
          if ( v10 == a2 )
            ++*a3;
        }
      }
      v6 = 0;
    }
    else
    {
      v6 = -2147024809;
    }
  }
  else
  {
    v6 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v11);
  return v6;
}

```

## disassembly

```asm
0x1800257d0  mov     [rsp+arg_8], rbx
0x1800257d5  mov     [rsp+arg_10], rbp
0x1800257da  push    rsi
0x1800257db  push    rdi
0x1800257dc  push    r14
0x1800257de  sub     rsp, 40h
0x1800257e2  movzx   ebp, dx
0x1800257e5  mov     rdi, rcx
0x1800257e8  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x1800257ec  mov     rbx, r8
0x1800257ef  lea     rcx, [rsp+58h+arg_0]; this
0x1800257f4  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x1800257f9  cmp     qword ptr [rdi+28h], 0
0x1800257fe  jnz     short loc_180025807
0x180025800  mov     ebx, 0C00D07F6h
0x180025805  jmp     short loc_180025863
0x180025807  test    rbx, rbx
0x18002580a  jnz     short loc_180025813
0x18002580c  mov     ebx, 80070057h
0x180025811  jmp     short loc_180025863
0x180025813  mov     eax, 0FFFFh
0x180025818  cmp     ax, bp
0x18002581b  jnz     short loc_180025829
0x18002581d  movzx   eax, word ptr [rdi+320h]
0x180025824  mov     [rbx], ax
0x180025827  jmp     short loc_180025861
0x180025829  xor     eax, eax
0x18002582b  xor     esi, esi
0x18002582d  mov     [rbx], ax
0x180025830  cmp     ax, [rdi+320h]
0x180025837  jnb     short loc_180025861
0x180025839  movzx   r8d, si
0x18002583d  lea     rdx, [rsp+58h+var_38]
0x180025842  lea     rcx, [rdi+50h]
0x180025846  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x18002584b  cmp     [rsp+58h+var_36], bp
0x180025850  jnz     short loc_180025855
0x180025852  inc     word ptr [rbx]
0x180025855  inc     si
0x180025858  cmp     si, [rdi+320h]
0x18002585f  jb      short loc_180025839
0x180025861  xor     ebx, ebx
0x180025863  lea     rcx, [rsp+58h+arg_0]; this
0x180025868  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002586d  mov     rbp, [rsp+58h+arg_10]
0x180025872  mov     eax, ebx
0x180025874  mov     rbx, [rsp+58h+arg_8]
0x180025879  add     rsp, 40h
0x18002587d  pop     r14
0x18002587f  pop     rdi
0x180025880  pop     rsi
0x180025881  retn
```
