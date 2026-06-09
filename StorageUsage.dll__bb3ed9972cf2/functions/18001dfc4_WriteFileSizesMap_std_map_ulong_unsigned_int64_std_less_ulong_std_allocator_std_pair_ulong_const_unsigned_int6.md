# WriteFileSizesMap(std::map<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>> *,SCAN_ID)

- ea: `0x18001dfc4`
- end: `0x18001e308`
- name: `?WriteFileSizesMap@@YAXPEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@W4SCAN_ID@@@Z`
- size: `836`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001ad40`

## callees

- `0x1800010b0`
- `0x18000263c`
- `0x180017dc8`
- `0x18001dfc4`

## pseudocode

```c
void __fastcall WriteFileSizesMap(__int64 a1, int a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // [rsp+D0h] [rbp-80h] BYREF
  int v7; // [rsp+D4h] [rbp-7Ch] BYREF
  int v8; // [rsp+D8h] [rbp-78h] BYREF
  int v9; // [rsp+DCh] [rbp-74h] BYREF
  int v10; // [rsp+E0h] [rbp-70h] BYREF
  int v11; // [rsp+E4h] [rbp-6Ch] BYREF
  int v12; // [rsp+E8h] [rbp-68h] BYREF
  int v13; // [rsp+ECh] [rbp-64h] BYREF
  int v14; // [rsp+F0h] [rbp-60h] BYREF
  int v15; // [rsp+F4h] [rbp-5Ch] BYREF
  int v16; // [rsp+F8h] [rbp-58h] BYREF
  int v17; // [rsp+FCh] [rbp-54h] BYREF
  int v18; // [rsp+100h] [rbp-50h] BYREF
  int v19; // [rsp+104h] [rbp-4Ch] BYREF
  int v20; // [rsp+108h] [rbp-48h] BYREF
  int v21; // [rsp+10Ch] [rbp-44h] BYREF
  int v22; // [rsp+110h] [rbp-40h] BYREF
  __int64 v23; // [rsp+118h] [rbp-38h] BYREF
  __int64 v24; // [rsp+120h] [rbp-30h] BYREF
  __int64 v25; // [rsp+128h] [rbp-28h] BYREF
  __int64 v26; // [rsp+130h] [rbp-20h] BYREF
  __int64 v27; // [rsp+138h] [rbp-18h] BYREF
  __int64 v28; // [rsp+140h] [rbp-10h] BYREF
  __int64 v29; // [rsp+148h] [rbp-8h] BYREF
  __int64 v30; // [rsp+150h] [rbp+0h] BYREF
  __int64 v31; // [rsp+158h] [rbp+8h] BYREF
  __int64 v32; // [rsp+160h] [rbp+10h] BYREF
  __int64 v33; // [rsp+168h] [rbp+18h] BYREF
  __int64 v34; // [rsp+170h] [rbp+20h] BYREF
  __int64 v35; // [rsp+178h] [rbp+28h] BYREF
  __int64 v36; // [rsp+180h] [rbp+30h] BYREF
  __int64 v37; // [rsp+188h] [rbp+38h] BYREF
  __int64 v38; // [rsp+190h] [rbp+40h] BYREF
  __int64 v39; // [rsp+198h] [rbp+48h] BYREF
  __int64 v40; // [rsp+1A0h] [rbp+50h] BYREF
  __int64 v41; // [rsp+1A8h] [rbp+58h] BYREF
  __int64 v42[4]; // [rsp+1B0h] [rbp+60h] BYREF
  int v43; // [rsp+1E0h] [rbp+90h] BYREF
  int v44; // [rsp+1F0h] [rbp+A0h] BYREF
  int v45; // [rsp+1F8h] [rbp+A8h] BYREF

  if ( a1 && (unsigned int)dword_180040010 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
    {
      v43 = 40;
      v23 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v43);
      v44 = 39;
      v24 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v44);
      v45 = 38;
      v25 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v45);
      v6 = 37;
      v26 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v6);
      v7 = 36;
      v27 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v7);
      v8 = 35;
      v28 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v8);
      v9 = 32;
      v29 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v9);
      v10 = 31;
      v30 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v10);
      v11 = 30;
      v31 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v11);
      v12 = 29;
      v32 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v12);
      v13 = 28;
      v33 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v13);
      v14 = 27;
      v34 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v14);
      v15 = 26;
      v35 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v15);
      v16 = 25;
      v36 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v16);
      v17 = 24;
      v37 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v17);
      v18 = 23;
      v38 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v18);
      v19 = 6;
      v39 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v19);
      v20 = 5;
      v40 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v20);
      v21 = 1;
      v41 = *(_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a1, (__int64)&v21);
      v22 = a2;
      v42[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v41,
        (__int64)byte_1800381A5,
        v4,
        v5,
        (__int64)v42,
        (__int64)&v22,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23);
    }
  }
}

```

## disassembly

```asm
0x18001dfc4  test    rcx, rcx
0x18001dfc7  jz      locret_18001E307
0x18001dfcd  push    rbp
0x18001dfce  push    rbx
0x18001dfcf  push    rdi
0x18001dfd0  lea     rbp, [rsp-70h]
0x18001dfd5  sub     rsp, 1C0h
0x18001dfdc  mov     eax, cs:dword_180040010
0x18001dfe2  mov     edi, edx
0x18001dfe4  mov     rbx, rcx
0x18001dfe7  cmp     eax, 5
0x18001dfea  jbe     loc_18001E2FD
0x18001dff0  mov     rdx, 400000000000h
0x18001dffa  lea     rcx, dword_180040010
0x18001e001  call    _tlgKeywordOn
0x18001e006  test    al, al
0x18001e008  jz      loc_18001E2FD
0x18001e00e  lea     rdx, [rbp+80h+arg_0]
0x18001e015  mov     [rbp+80h+arg_0], 28h ; '('
0x18001e01f  mov     rcx, rbx
0x18001e022  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e027  lea     rdx, [rbp+80h+arg_10]
0x18001e02e  mov     rcx, [rax]
0x18001e031  mov     [rbp+80h+var_B8], rcx
0x18001e035  mov     rcx, rbx
0x18001e038  mov     [rbp+80h+arg_10], 27h ; '''
0x18001e042  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e047  lea     rdx, [rbp+80h+arg_18]
0x18001e04e  mov     rcx, [rax]
0x18001e051  mov     [rbp+80h+var_B0], rcx
0x18001e055  mov     rcx, rbx
0x18001e058  mov     [rbp+80h+arg_18], 26h ; '&'
0x18001e062  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e067  lea     rdx, [rbp+80h+var_100]
0x18001e06b  mov     rcx, [rax]
0x18001e06e  mov     [rbp+80h+var_A8], rcx
0x18001e072  mov     rcx, rbx
0x18001e075  mov     [rbp+80h+var_100], 25h ; '%'
0x18001e07c  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e081  lea     rdx, [rbp+80h+var_FC]
0x18001e085  mov     rcx, [rax]
0x18001e088  mov     [rbp+80h+var_A0], rcx
0x18001e08c  mov     rcx, rbx
0x18001e08f  mov     [rbp+80h+var_FC], 24h ; '$'
0x18001e096  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e09b  lea     rdx, [rbp+80h+var_F8]
0x18001e09f  mov     rcx, [rax]
0x18001e0a2  mov     [rbp+80h+var_98], rcx
0x18001e0a6  mov     rcx, rbx
0x18001e0a9  mov     [rbp+80h+var_F8], 23h ; '#'
0x18001e0b0  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e0b5  lea     rdx, [rbp+80h+var_F4]
0x18001e0b9  mov     rcx, [rax]
0x18001e0bc  mov     [rbp+80h+var_90], rcx
0x18001e0c0  mov     rcx, rbx
0x18001e0c3  mov     [rbp+80h+var_F4], 20h ; ' '
0x18001e0ca  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e0cf  lea     rdx, [rbp+80h+var_F0]
0x18001e0d3  mov     rcx, [rax]
0x18001e0d6  mov     [rbp+80h+var_88], rcx
0x18001e0da  mov     rcx, rbx
0x18001e0dd  mov     [rbp+80h+var_F0], 1Fh
0x18001e0e4  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e0e9  lea     rdx, [rbp+80h+var_EC]
0x18001e0ed  mov     rcx, [rax]
0x18001e0f0  mov     [rbp+80h+var_80], rcx
0x18001e0f4  mov     rcx, rbx
0x18001e0f7  mov     [rbp+80h+var_EC], 1Eh
0x18001e0fe  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e103  lea     rdx, [rbp+80h+var_E8]
0x18001e107  mov     rcx, [rax]
0x18001e10a  mov     [rbp+80h+var_78], rcx
0x18001e10e  mov     rcx, rbx
0x18001e111  mov     [rbp+80h+var_E8], 1Dh
0x18001e118  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e11d  lea     rdx, [rbp+80h+var_E4]
0x18001e121  mov     rcx, [rax]
0x18001e124  mov     [rbp+80h+var_70], rcx
0x18001e128  mov     rcx, rbx
0x18001e12b  mov     [rbp+80h+var_E4], 1Ch
0x18001e132  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e137  lea     rdx, [rbp+80h+var_E0]
0x18001e13b  mov     rcx, [rax]
0x18001e13e  mov     [rbp+80h+var_68], rcx
0x18001e142  mov     rcx, rbx
0x18001e145  mov     [rbp+80h+var_E0], 1Bh
0x18001e14c  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e151  lea     rdx, [rbp+80h+var_DC]
0x18001e155  mov     rcx, [rax]
0x18001e158  mov     [rbp+80h+var_60], rcx
0x18001e15c  mov     rcx, rbx
0x18001e15f  mov     [rbp+80h+var_DC], 1Ah
0x18001e166  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e16b  lea     rdx, [rbp+80h+var_D8]
0x18001e16f  mov     rcx, [rax]
0x18001e172  mov     [rbp+80h+var_58], rcx
0x18001e176  mov     rcx, rbx
0x18001e179  mov     [rbp+80h+var_D8], 19h
0x18001e180  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e185  lea     rdx, [rbp+80h+var_D4]
0x18001e189  mov     rcx, [rax]
0x18001e18c  mov     [rbp+80h+var_50], rcx
0x18001e190  mov     rcx, rbx
0x18001e193  mov     [rbp+80h+var_D4], 18h
0x18001e19a  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e19f  lea     rdx, [rbp+80h+var_D0]
0x18001e1a3  mov     rcx, [rax]
0x18001e1a6  mov     [rbp+80h+var_48], rcx
0x18001e1aa  mov     rcx, rbx
0x18001e1ad  mov     [rbp+80h+var_D0], 17h
0x18001e1b4  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e1b9  lea     rdx, [rbp+80h+var_CC]
0x18001e1bd  mov     rcx, [rax]
0x18001e1c0  mov     [rbp+80h+var_40], rcx
0x18001e1c4  mov     rcx, rbx
0x18001e1c7  mov     [rbp+80h+var_CC], 6
0x18001e1ce  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e1d3  lea     rdx, [rbp+80h+var_C8]
0x18001e1d7  mov     rcx, [rax]
0x18001e1da  mov     [rbp+80h+var_38], rcx
0x18001e1de  mov     rcx, rbx
0x18001e1e1  mov     [rbp+80h+var_C8], 5
0x18001e1e8  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e1ed  lea     rdx, [rbp+80h+var_C4]
0x18001e1f1  mov     rcx, [rax]
0x18001e1f4  mov     [rbp+80h+var_30], rcx
0x18001e1f8  mov     rcx, rbx
0x18001e1fb  mov     [rbp+80h+var_C4], 1
0x18001e202  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001e207  lea     rdx, byte_1800381A5
0x18001e20e  mov     rcx, [rax]
0x18001e211  lea     rax, [rbp+80h+var_B8]
0x18001e215  mov     [rsp+1D0h+var_110], rax
0x18001e21d  lea     rax, [rbp+80h+var_B0]
0x18001e221  mov     [rsp+1D0h+var_118], rax
0x18001e229  lea     rax, [rbp+80h+var_A8]
0x18001e22d  mov     [rsp+1D0h+var_120], rax
0x18001e235  lea     rax, [rbp+80h+var_A0]
0x18001e239  mov     [rsp+1D0h+var_128], rax
0x18001e241  lea     rax, [rbp+80h+var_98]
0x18001e245  mov     [rsp+1D0h+var_130], rax
0x18001e24d  lea     rax, [rbp+80h+var_90]
0x18001e251  mov     [rsp+1D0h+var_138], rax
0x18001e259  lea     rax, [rbp+80h+var_88]
0x18001e25d  mov     [rsp+1D0h+var_140], rax
0x18001e265  lea     rax, [rbp+80h+var_80]
0x18001e269  mov     [rsp+1D0h+var_148], rax
0x18001e271  lea     rax, [rbp+80h+var_78]
0x18001e275  mov     [rsp+1D0h+var_150], rax
0x18001e27d  lea     rax, [rbp+80h+var_70]
0x18001e281  mov     [rsp+1D0h+var_158], rax
0x18001e286  lea     rax, [rbp+80h+var_68]
0x18001e28a  mov     [rsp+1D0h+var_160], rax
0x18001e28f  lea     rax, [rbp+80h+var_60]
0x18001e293  mov     [rsp+1D0h+var_168], rax
0x18001e298  lea     rax, [rbp+80h+var_58]
0x18001e29c  mov     [rsp+1D0h+var_170], rax
0x18001e2a1  lea     rax, [rbp+80h+var_50]
0x18001e2a5  mov     [rsp+1D0h+var_178], rax
0x18001e2aa  lea     rax, [rbp+80h+var_48]
0x18001e2ae  mov     [rsp+1D0h+var_180], rax
0x18001e2b3  lea     rax, [rbp+80h+var_40]
0x18001e2b7  mov     [rsp+1D0h+var_188], rax
0x18001e2bc  lea     rax, [rbp+80h+var_38]
0x18001e2c0  mov     [rsp+1D0h+var_190], rax
0x18001e2c5  lea     rax, [rbp+80h+var_30]
0x18001e2c9  mov     [rsp+1D0h+var_198], rax
0x18001e2ce  lea     rax, [rbp+80h+var_28]
0x18001e2d2  mov     [rsp+1D0h+var_1A0], rax
0x18001e2d7  lea     rax, [rbp+80h+var_C0]
0x18001e2db  mov     [rsp+1D0h+var_1A8], rax
0x18001e2e0  lea     rax, [rbp+80h+var_20]
0x18001e2e4  mov     [rsp+1D0h+var_1B0], rax
0x18001e2e9  mov     [rbp+80h+var_28], rcx
0x18001e2ed  mov     [rbp+80h+var_C0], edi
0x18001e2f0  mov     [rbp+80h+var_20], 1000000h
0x18001e2f8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@3333333333333333333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18001e2fd  add     rsp, 1C0h
0x18001e304  pop     rdi
0x18001e305  pop     rbx
0x18001e306  pop     rbp
0x18001e307  retn
```
